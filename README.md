<img src="https://user-images.githubusercontent.com/1423657/218816262-e0e8d7ad-44d0-4a7d-9497-0d383ed78b83.png" width=150>

# qryn-chdb
qryn + chdb experiments

<br>

### Launch
Spin up qryn w/ chdb storage
```
docker compose up -d
```

### Test
Send a sample log line
```
curl -i -XPOST -H "Content-Type: application/json" http://localhost:3100/loki/api/v1/push \
  --data '{"streams":[{"stream":{"type":"test"},"values":[['$(date +"%s%N")', "hello qryn"]]}]}'
```

Find your test log using qryn-view

![image](https://github.com/metrico/qryn-chdb/assets/1423657/d05e0442-08de-486c-85de-e3d69b87716c)
