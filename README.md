# kibana

Start all services
```bash
docker-compose up -d
```

Install X-Pack plugin
```bash
docker-compose exec elasticsearch bin/elasticsearch-plugin install x-pack
```

Change passwords (= 5.0)
```bash
docker-compose exec elasticsearch curl -u elastic:changeme -XPUT 0.0.0.0:9200/_xpack/security/user/elastic/_password -d '{"password": "secret"}'
docker-compose exec elasticsearch curl -u elastic:secret -XPUT 0.0.0.0:9200/_xpack/security/user/kibana/_password -d '{"password": "secret"}'
```

Change passwords (= 6.0)
```bash
docker-compose exec elasticsearch bin/x-pack/setup-passwords interactive
```

Change passwords (> 6.0)
```bash
docker-compose exec elasticsearch bin/elasticsearch-setup-passwords interactive
```
