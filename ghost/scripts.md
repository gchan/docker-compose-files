### Manual Backup
```shell
docker run -v ghost_ghost_data:/var/lib/ghost \
  --rm=true \
  -v /tmp:/tmp \
  ubuntu \
  tar zcvf /tmp/ghost-backup-$(date +%Y-%m-%d).tar.gz /var/lib/ghost
```

```shell
docker-machine scp docker:/tmp/ghost-backup-$(date +%Y-%m-%d).tar.gz ./backup/.
```

### Restore from local file
```shell
docker-machine scp ./backup/ghost-backup-2016-08-09.tar.gz docker:/tmp/.
```

```shell
docker run -v ghost_ghost_data:/var/lib/ghost \
  --rm=true \
  -v /tmp:/tmp \
  ubuntu \
  tar zxvf /tmp/ghost-backup-2016-08-09.tar.gz
```

### Restore from automated backups
```shell
docker exec -it ghost_ghost_backup_1 restore -i
```

### View data volume
```shell
docker run -v ghost_ghost_data:/var/lib/ghost \
  --rm=true \
  -it \
  ubuntu
```
