# Backup
```shell
docker run --volumes-from ghost_data_1 \
  --rm=true \
  -v $(pwd):/backup \
  ubuntu \
  tar zcvf /backup/ghost-backup.tar.gz /var/lib/ghost
```

```shell
docker run --volumes-from ghost_data_1 \
  --rm=true \
  -v $(pwd):/backup \
  ubuntu \
  tar zcvf /backup/ghost-backup-$(date +%Y-%m-%d).tar.gz /var/lib/ghost
```

# Restore
```shell
docker run --volumes-from ghost_data_1 \
  --rm=true \
  -v $(pwd):/backup \
  ubuntu \
  tar zxvf /backup/ghost-backup-$(date +%Y-%m-%d).tar.gz
```

# Install custom theme
```shell
docker run --volumes-from ghost_data_1 \
  --rm=true \
  -v $(pwd):/backup \
  ubuntu \
  sh -c 'cp -r /backup/gchan-casper /var/lib/ghost/themes && \
    rm -rf /var/lib/ghost/themes/gchan-casper/.*'
```

# View data volume
```shell
docker run --volumes-from ghost_data_1 \
  --rm=true \
  -v $(pwd):/backup \
  -it \
  ubuntu
```
