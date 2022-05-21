### Cloudflare Workers反代

   **单双日交替使用不同dyno绕过Heroku非信用卡验证账号每月550小时限制**

- 需要两个Heroku账号分别部署使用相同变量设置的dyno
- 登陆cloudflare账号
- 点击左侧导航栏workers，选择Create a Service
- 创建service以后，点击Quick Edit
- 将如下代码粘贴进左侧编辑区

 ```
const SingleDay = 'cloud1.herokuapp.com'
const DoubleDay = 'cloud2.herokuapp.com'
const timezone = 'Etc/GMT+2'; 

addEventListener(
    "fetch",event => { 

        let localized_date = new Date(new Date().toLocaleString('en-US', { timeZone: timezone }));
        if (localized_date.getDate()%2) {
            host = SingleDay
        } else {
            host = DoubleDay
        }

        let url=new URL(event.request.url);
        url.hostname=host;
        let request=new Request(url,event.request);
        event. respondWith(
            fetch(request)
        )
    }
)
```

- 第一行和第二行分别填单双日所使用的Heroku dyno域名，第三行是通过时区控制切换dyno的时间，范围从Etc/GMT-12到Etc/GMT+12。
- 点击Save and Deploy即可生效。
