<img src="https://raw.githubusercontent.com/crisward/dokku-clone/master/clone-logo.png?v=2" />

A dokku plugin which allows you to create an app from a git url


## Requirements

* dokku 0.4.0+

## Installation

```bash
# on 0.4.x
dokku plugin:install https://github.com/crisward/dokku-clone.git clone
```

## Usage

```bash
# create or update and app from eg github
dokku@dokku.me clone yourapp https://github.com/you/yourproject.git

#eg 
ssh dokku@dokku.me apps:create nodetest
ssh dokku@dokku.me clone nodetest https://github.com/heroku/node-js-getting-started.git

# you'll then have the heroku sample app on nodetest.dokku.me (you may have to update your hosts file)
```

### Private Repos / git urls

If you need to clone private repos, or just want to use git@ urls you'll need to add a deploy key to your git provider (ie github).
If you want to be able to pull any repo from github, you'll have to add the key [here](https://github.com/settings/ssh)
Clone creates a fresh keypair when the plugin is first installed. The public part of the key can be accessed with.

```bash
# output with
ssh dokku@dokku.me clone:key

# save to clipboard with (mac only)
ssh dokku@dokku.me clone:key | pbcopy

# before cloning the repo, you'll need to add the remote to known hosts with
ssh dokku@dokku.me clone:allow github.com

```

## Credits

Thanks to [Jose Gonzalez](https://github.com/josegonzalez) for the Dokku5 refactor
and the [Noun Project](https://thenounproject.com/) for the logo


## License

(The MIT License)

Copyright (c) 2016 Cris Ward

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the 'Software'), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.