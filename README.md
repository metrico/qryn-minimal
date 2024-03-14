<img src="https://user-images.githubusercontent.com/1423657/218816262-e0e8d7ad-44d0-4a7d-9497-0d383ed78b83.png" width=180>

# qryn-minimal

> The lightest, most portable and powerful _all-in-one_ observability combo ever made.

<br>

### ⭐ Features
Drop-in compatible ingestion and query APIs with polyglot features:
- **Loki** API + **LogQL**
- **Prometheus** API + **PromQL**
- **Tempo** API + **TempoQL**
- **Pyroscope** API
- **Ingestion** APIs for Elastic, Datadog, InfluxDB, etc

<br>

### 🍪 Ingredients
- **[qryn](https://github.com/metrico/qryn)**: _polyglot, lighweight, multi-standard drop-in observability framework for Logs, Metrics and Traces_
- **[qryn](https://github.com/cowsdb/cowsdb)**: _local embedded SQL OLAP Engine for serverless functions API compatible with ClickHouse_


<br>

### 👉 Launch

##### ⚠️ This bundle is experimental and only suitable for minimal single nodes and local storage.

Spin up qryn-minimal w/ onboard storage using `docker compose`
```
docker compose pull
docker compose up -d
```

| app | port |
|---|---|
| qryn | 3100 |

<br>

### 🔎 Test
- Ingest a sample log line using `curl`
```
curl -i -XPOST -H "Content-Type: application/json" http://localhost:3100/loki/api/v1/push \
  --data '{"streams":[{"stream":{"type":"test"},"values":[['$(date +"%s%N")', "hello qryn"]]}]}'
```

- Browse to `http://localhost:3100` and find your test log using the `qryn-view` interface

<img src="https://github.com/metrico/qryn-minimal/assets/1423657/d05e0442-08de-486c-85de-e3d69b87716c" width=400 >

- Follow the [qryn instructions](https://qryn.metrico.in/#/) to ingest any of your **Logs, Metrics and Traces**
- Add **Grafana** using the native _Loki, Prometheus and Tempo datasources_ with **qryn** APIs
