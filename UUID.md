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