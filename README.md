# PHP - Discord Nitro Checker API

### Documention : [https://nitro-gift.nankaji-dev.tk/](https://nitro-gift.nankaji-dev.tk/)

### Demo : [https://nitro-gift.nankaji-dev.tk/demo.php](https://nitro-gift.nankaji-dev.tk/demo.php)

## Github Documention :

### API url : `https://nitro-gift.nankaji-dev.tk/api/nitro-checker/{code}`

Example ajax code (jQuery) :

```javascript
$.get(`https://nitro-gift.nankaji-dev.tk/api/nitro-checker/zjnOmBuYgXcuGPyU`, function (data, status) {
    if (status == "success") {
      if (data.status == 404) {
        // Invalid
      } else if (data.status == 427) {
        // Cooldown
      } else if (data.status == 200) {
        if (!data.claimed) {
          // Valid and Available
        } else {
          // Invalid and Unavailable
        }
      }
    } else {
      // Error
    }
});
```

## Example JSON Response :

Status code : 200 (Available)

```json
{
    "message": "Code is valid !",
    "status": 200,
    "claimed": false
}
```

Status code : 200 (Used)

```json
{
    "message": "Code is valid but this code is being used !",
    "status": 200,
    "claimed": true
}
```

Status code : 404 (Invalid)

```json
{
    "message": "Code is invalid !",
    "status": 404
}
```

Status code : 0 (Missing Information)

```json
{
    "message": "MISSING_INFORMATION",
    "status": 0
}
```

Status code : 100 (Minimum Length)

```json
{
    "message": "Value must be more than 16 characters !",
    "status": 100
}
```

Status code : 101 (Maximum Length)

```json
{
    "message": "Value must be less than 30 characters !",
    "status": 101
}
```

Status code : 429 (Cooldown)

```json
{
    "message": "Wait for cooldown 15(s)",
    "status": 429,
    "countdown": 15
}
```

Status code : -1 (Unknown)

```json
{
    "message": "Unknown status",
    "status": -1
}
```

## Contact me

Facebook : `[https://www.facebook.com/Nankaji.Minato/](https://www.facebook.com/Nankaji.Minato/)`

Email : `kuromi.dev@tokovn.com`
