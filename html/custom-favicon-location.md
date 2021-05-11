# Custom favicon location

Browsers look for shortcut icon at `/favicon.ico`.

Custom location useful when static assets are served at a different endpoint (e.g. when using FastAPI).

```html
<link rel="shortcut icon" href="/static/favicon.ico">
```

