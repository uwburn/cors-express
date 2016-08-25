# CORS middleware

A simple Express middleware to enable cross origin resource sharing on a route. It will deals with `access-control-allow-origin`, `access-control-allow-credentials`, `access-control-request-headers` and `access-control-allow-methods` headers. `OPTIONS` preflight requests will be directly answered with a `HTTP 200 - OK`.

### Usage

```javascript
var Express = require('express');
var cors = require('cors');

var app = Express();

express.use(cors({
    allowWithoutOrigin: true,
    onlyAllowedOrigin: true,
    allowCredentials: true,
	allowedOrigins: [
		'http://127.0.0.1:8181',
		'http://localhost:8181'
	],
	nullOrigin: 'null'
}));
```

### Options
- `allowWithoutOrigin`: if `true`, allow requests without origin, setting `access-control-allow-origin=*`
- `onlyAllowedOrigin`: if `true`, requires the origin to be in the list of allowed origins
- `allowCredentials`: if `true`, will set `access-control-allow-credentials=true`
- `allowedOrigins`: an array of string representing the allowed origins
- `nullOrigin`: set the string corresponding to `null` origin, most likely the default will always be ok
