### Cloudflare Workers反代

- Workers.dev域名在大陆地区被sni阻断，无法直接访问https服务。可以使用Workers Route功能绑定自定义域名。
- 登陆cloudflare账号
- 点击左侧导航栏workers，选择Create a Service
- 创建service以后，点击Quick Edit
- 将如下代码粘贴进左侧编辑区

 ```
const host = 'example.example.com';

addEventListener(
   "fetch",event => { 

       let url=new URL(event.request.url);
       url.hostname=host;
       let request=new Request(url,event.request);
       event. respondWith(
           fetch(request)
       )
   }
)
```

- 第一行填写需要反代的域名。
- 点击Save and Deploy即可生效。
