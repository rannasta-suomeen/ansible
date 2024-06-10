# Robust deployment infrastructure for rannasta-suomeen

## Deployment setup
1. Create `./hosts` file. Define your remote server host
```yaml
# ./hosts
server_main = server_main ansible_host=0.0.0.0 ansible_user=user
```

2. Create `vault/vault.yml` file. Define your secrets there
```yaml
# ./vault/vault.yml
- user: user
- cr_pat: <generate with github>
- pg_password: very_secret_password
```
* (You sould encrypt the vault with `ansible-vault encrypt ./vault/vault.yml`)
    
3. Create `.password` for remote host sudo-password (as well as for vault password). File should **only** contain the password *(in plaintext)*