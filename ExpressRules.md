## Allows a way to define Express rules. Properties from both req and res could be mentioned as keys.

```
require('honeycomb-beeline')({
  writeKey: 'your write key comes here',
  dataset: 'your dataset comes here',
  express: {
    rules: [
      { key: 'path', condition: '===', value: '/api/v1/healthcheck', sampleRate: 10000 },
      { key: 'statusCode', condition: '===', value: 200, sampleRate: 100 },
      { key: 'statusCode', condition: '<', value: 500, sampleRate: 5 },
// all requests not filtered by the rules above will have a sampleRate of 1
    ],
  },
});
```
