
Basic chat


```sh
curl https://hazai.kaja.io/api/generate -d '{
  "model": "smollm2",
  "prompt":"Why is the sky blue?"
}'
```

POST message

```sh
curl -k -N -X POST https://static.249.244.62.46.clients.your-server.de/api/chat/stream -H "Content-Type: application/json" -d '{"message":"continue"}'
```
