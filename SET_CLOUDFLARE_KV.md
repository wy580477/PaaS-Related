 1. Open [Cloudflare Workers KV](https://dash.cloudflare.com/workers/kv "Cloudflare Workers KV") Page
 2. Click on Manage KV namespaces, then create a namespace.
 3. Now click on Workers & Create a workers service.
 4. Copy the code of <code>[worker.js](https://github.com/wy580477/CloudflareDB/blob/main/worker.js "worker.js")</code> , paste code into Workers service editor and set your own KEY & GETKEY value ( the two values must be same ). Then Click on Save & Deploy.
 5. Now go back to your Workers service main page, Click on <code>Settings</code>.
 6. Click on <code>Variables</code>, in <code>KV Namespace Bindings</code> section click on <code>Add Binding</code>.
 7. Write <code>JSONBASE</code> in Variable name & select your recently created Namespace for KV namespace.
