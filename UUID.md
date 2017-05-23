[InstaUUID](https://github.com/therne/instauuid)
[Ruid](https://github.com/trekjs/ruid)
[uniqueid](https://github.com/jonschlinkert/uniqueid)

```javascript
function uuid() {
  let _ = ''
  let possible = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789'
  for (let i = 0; i < 16; i++) {
      _ += possible.charAt(Math.floor(Math.random() * possible.length))
  }
  
  return _
}
```

OR 
```javascript
const b = a => a ? (a ^ Math.random() * 16 >> a / 4).toString(16) : ([1e7] + -1e3 + -4e3 + -8e3 + -1e11).replace(/[018]/g, b)
module.exports = b
```
