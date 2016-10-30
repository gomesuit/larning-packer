# example

```
packer build \
  -var git_commit_id=$(git rev-parse HEAD) \
  ansible-remote.template
```

