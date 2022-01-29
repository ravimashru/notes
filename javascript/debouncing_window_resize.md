# Debouncing the window resize event

```javascript
window.addEventListener('resize', () => {

    window.clearTimeout(window.resizeTimeout)

    window.resizeTimeout = window.setTimeout(() => {

        doSomething()

    }, 500)

})
```

Source: https://perdjurner.com/#/debouncing-the-window-resize-event