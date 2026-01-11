# Homelab Core Services

- Mostly networking but also git.
- Setup as a github mirror to bootstrap the rest through gitea.

## Backups

```
tar cvvzf /tank/tmp/immich-`date +%F`.tar.gz /tank/services/immich
aws s3 cp /tank/tmp/immich-`date +%F`.tar.gz \
  s3://nvengal-homelab-backups/immich-`date +%F`.tar.gz \
  --storage-class DEEP_ARCHIVE

tar czf /tank/tmp/gitea-`date +%F`.tar.gz /tank/services/gitea
aws s3 cp /tank/tmp/gitea-`date +%F`.tar.gz \
  s3://nvengal-homelab-backups/gitea-`date +%F`.tar.gz \
  --storage-class DEEP_ARCHIVE
```

## TODO

- Glacier backups
- Switch from gitea->forgejo
