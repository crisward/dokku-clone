!! In Development

# Dokku Gitclone

A dokku plugin which allows you to create an app from a git url


## Requirements

* dokku 0.4.0+

## Installation

```bash
# on 0.4.x
dokku plugin:install https://github.com/crisward/dokku-gitclone.git gitclone
```

## Usage

```bash
# create or update and app from eg github
dokku@dokku.me gitclone yourapp https://github.com/you/yourproject.git

#eg 
ssh dokku@dokku.me apps:create nodetest
ssh dokku@dokku.me gitclone nodetest https://github.com/heroku/node-js-getting-started.git

# you'll then have the heroku sample app on nodetest.dokku.me (you may have to update your hosts file)
```

### Private Repos

If you need to clone private repos you'll need to add a deploy key to your git provider (ie github).
Gitclone creates a fresh keypair when the plugin is first installed. The public part of the key can be accessed with.

```bash
# output with
ssh dokku@dokku.me gitclone:key

# save to clipboard with (mac only)
ssh dokku@dokku.me gitclone:key | pbcopy
```


