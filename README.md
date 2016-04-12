!! In Development

# Dokku Gitclone

A dokku plugin which allows you to create an app from a git url


## Requirements

* dokku 0.4.0+

## Installation

```
# on 0.4.x
dokku plugin:install https://github.com/crisward/dokku-gitclone.git gitclone
```

## Usage

```
# create or update and app from eg github
dokku@yoursever.com gitclone yourapp https://github.com/you/yourproject.git
```



