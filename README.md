
Learn more about summon here:
https://conjurinc.github.io/summon/

A secrets provider for summon using lastpass as a backend
All interaction with lastpass is done through the lastpass-cli.
Secrets are stored as 'secret notes'

# Install and setup lastpass-cli
 Follow instructions here: https://github.com/lastpass/lastpass-cli

# Login
lpass login <email>

# Adding new secrets
lpass add --sync now --notes "secrets/$environment/mariadb/username"

# Running Summon
summon --provider lastpass -f secrets.yml chef-client --once
summon --provider lastpass -f secrets.yml docker run --env-file @SUMMONENVFILE myap

