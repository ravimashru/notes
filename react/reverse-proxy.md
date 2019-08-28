# Using a Reverse Proxy with React App

**Step 1** - Create a regular reverse proxy using `express` and `http-proxy-middleware`:

```javascript
const proxy = require('http-proxy-middleware');
const express = require('express');

const options = {
  target: 'http://target.domain.com:1080',
  changeOrigin: true
};

const proxyServer = proxy(options);
const app = express();

app.use('/api', (req, res, next) => {
  console.log('Request proxied...');
  next();
}, proxyServer);

app.listen(8080, () => {
  console.log('Server started...');
});
```



**Step 2** - Add `proxy` property to `package.json`:

```json
{
  ...
  "proxy": "http://localhost:8080"
  ...
}
```



That's it. Honestly, it's that simple! Any requests to a path starting with `/api` will now go through the reverse proxy. 🎉



Sources:

- https://www.twilio.com/blog/react-app-with-node-js-server-proxy