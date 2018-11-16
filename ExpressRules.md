## Allows a way to define Express rules. Properties from req, res and durationMs could be used.

```
require('honeycomb-beeline')({
  writeKey: 'your write key comes here',
  dataset: 'your dataset comes here',
  express: {
    rules: [
      { condition: 'req.path === "/api/v1/healthcheck"', sampleRate: 10000 },
      { condition: 'res.statusCode === 200 && durationMs > 1000', sampleRate: 5 },
      { condition: 'res.statusCode >= 500', sampleRate: 1 },
      // all requests not filtered by the rules above will have a sampleRate of process.env['HONEYCOMB_SAMPLERATE'] or 1 if not defined
    ],
  },
});
```
