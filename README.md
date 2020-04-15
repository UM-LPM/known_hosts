# ```known_hosts```

This repo contains SSH host keys of our servers.

## Setup

Modify github actions to install the ```known_hosts``` file
```yaml
- uses: actions/checkout@v2
  with:
    repository: UM-LPM/known_hosts
    path: known_hosts

- name: Set known hosts
  run: install -D -m 400 known_hosts/known_hosts ~/.ssh/known_hosts
```
