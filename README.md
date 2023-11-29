<img src="https://user-images.githubusercontent.com/1423657/218816262-e0e8d7ad-44d0-4a7d-9497-0d383ed78b83.png" width=180>

# qryn `+` chdb

> The lightest, most portable and powerful observability combo ever

#### ⭐ Ingredients
- **qryn**: _polyglot, lighweight, multi-standard drop-in observability framework for Logs, Metrics and Traces_
- **chdb**: _embedded SQL OLAP Engine for serverless functions powered by and compatible with ClickHouse_

<br>

### 👉 Launch
Spin up qryn w/ chdb storage
```
docker compose up -d
```

### 🔎 Test
Ingest a sample log line using `curl`
```
curl -i -XPOST -H "Content-Type: application/json" http://localhost:3100/loki/api/v1/push \
  --data '{"streams":[{"stream":{"type":"test"},"values":[['$(date +"%s%N")', "hello qryn"]]}]}'
```

Find your test log using `qryn-view`

<img src="https://github.com/metrico/qryn-chdb/assets/1423657/d05e0442-08de-486c-85de-e3d69b87716c" width=400 >
