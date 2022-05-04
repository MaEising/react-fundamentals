# React Fundamentals

### Render Hello World with JavaScript

```
<body>
  <script type="module">
    var rootdiv = document.createElement('div')
    rootdiv.setAttribute('id', 'root')
    document.body.append(rootdiv)
    var mydiv = document.createElement('div')
    mydiv.textContent = 'Hello World!'
    mydiv.className = 'container'
    rootdiv.append(mydiv)
  </script>
</body>
```
