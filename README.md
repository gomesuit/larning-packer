# example

## 実行
```
packer build \
  -var git_commit_id=$(git rev-parse HEAD) \
  ansible-remote.template
```

## ami-idを抽出する
```
packer build \
  -var git_commit_id=$(git rev-parse HEAD) \
  ansible-remote.template \
  -machine-readable \
  | awk -F , '$2 ~ /^amazon-ebs$/ && $3 ~ /^artifact$/ && $5 ~ /^id$/ {print $6}' | awk -F : '{print $2}'
```

