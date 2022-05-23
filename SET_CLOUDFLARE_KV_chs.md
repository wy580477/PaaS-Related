1. 打开 [Cloudflare Workers KV](https://dash.cloudflare.com/workers/kv "Cloudflare Workers KV")
2. 点击创建命名空间, 然后建立一个命名空间。
3. 点击Workers，建立一个Workers服务。
4. 将此链接 <code>[worker.js](https://github.com/wy580477/CloudflareDB/blob/main/worker.js "worker.js")</code> 中代码复制进Workers服务编辑器，将KEY和GETKEY值更换为一个自定义密钥，然后保存并部署。
5. 回到Workers服务主页面，点击设置--变量--KV命名空间绑定--添加绑定，变量名称填JSONBASE，选择刚才建立的KV命名空间，然后保存。
