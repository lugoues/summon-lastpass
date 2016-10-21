
Learn more about summon here:
https://conjurinc.github.io/summon/

A secrets provider for summon using lastpass as a backend
All interaction with lastpass is done through the lastpass-cli.
Secrets are stored as 'secret notes'

### Install and setup lastpass-cli
Follow instructions here: https://github.com/lastpass/lastpass-cli

### Install lastpass povider
`wget "https://raw.githubusercontent.com/Lugoues/summon-lastpass/master/lastpass" -O /usr/local/lib/summon/lastpass`

### Login
`lpass login <email>`

### Adding new secrets
`lpass add --sync now --notes "secrets/mariadb/password"`

### Create a secrets file
```
---
MYSQL_ROOT_PASSWORD: !var secrets/mariadb/password
```

### Running Summon
`summon --provider lastpass -f secrets.yml docker run --name some-mariadb --env-file @SUMMONENVFILE  -d mariadb:tag`

`--provider lastpass` is optional if it is the only provider installed
`-f secrets.yml` is optional if secrets.yml is in your current directory
