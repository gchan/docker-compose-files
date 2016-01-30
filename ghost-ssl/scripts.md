### Backup
```shell
docker run --volumes-from ghostssl_ghost_data_1 \
  --rm=true \
  -v $(pwd):/backup \
  ubuntu \
  tar zcvf /backup/ghost-backup.tar.gz /var/lib/ghost
```

```shell
docker run --volumes-from ghostssl_ghost_data_1 \
  --rm=true \
  -v $(pwd):/backup \
  ubuntu \
  tar zcvf /backup/ghost-backup-$(date +%Y-%m-%d).tar.gz /var/lib/ghost
```

```shell
docker cp ghostssl_ghost_data_1:/var/lib/ghost/ ./backup/ghost-$(date +%Y-%m-%d)
```

```shell
docker cp ghostssl_ghost_backup_data_1:/backups/ ./backup/
```

### Restore
```shell
docker run --volumes-from ghostssl_ghost_data_1 \
  --rm=true \
  -v $(pwd):/backup \
  ubuntu \
  tar zxvf /backup/ghost-backup.tar.gz
```

```shell
docker cp ./backup/ghost-$(date +%Y-%m-%d)/. ghostssl_ghost_data_1:/var/lib/ghost
```

```shell
docker cp ./backup/backups/. ghostssl_ghost_backup_data_1:/backups/
docker exec -it ghostssl_ghost_backup_1 restore -i
```

### Install custom theme
```shell
docker run --volumes-from ghostssl_ghost_data_1 \
  --rm=true \
  -v $(pwd):/backup \
  ubuntu \
  sh -c 'cp -r /backup/gchan-casper /var/lib/ghost/themes && \
    rm -rf /var/lib/ghost/themes/gchan-casper/.*'
```

### View data volume
```shell
docker run --volumes-from ghostssl_ghost_data_1 \
  --rm=true \
  -v $(pwd):/backup \
  -it \
  ubuntu
```
