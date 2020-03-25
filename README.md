# ```known_hosts```

This repo contains SSH host keys of our servers.

## Setup

Metavariables: ```<path>```

1. Clone this repository somewhere inside your main repository

```bash
git -C '<path>' clone https://github.com/UM-LPM/known_hosts.git 
```

2. Add the path to the nested repository to ```.gitignore```

```bash
echo '<path>/known_hosts/' >> .gitignore
```

3. Modify github actions to also clone the nested repository

```yaml
- uses: actions/checkout@v2
  with:
    repository: UM-LPM/known_hosts 
    path: <path>/known_hosts
```

4. When using ```ssh``` use to the ```known_hosts``` file from this repository

```
ssh -o UserKnownHostsFile <path>/known_hosts/known_hosts
```
