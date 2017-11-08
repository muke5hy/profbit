# profbit
[![Circle CI](https://circleci.com/gh/joshblum/profbit.svg?maxAge=2592000&style=shield)](https://circleci.com/gh/joshblum/profbit)

Find out what your Coinbase profits are!

## Development/Self-hosted Server Setup

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)


### Requirements
We use [Pipenv](http://docs.python-guide.org/en/latest/dev/virtualenvs/) to
manage requirements.

```bash
pip install pipenv
pipenv install
pipenv shell
```

### Server Config
You will first have [register an application on
Coinbase](https://coinbase.com/oauth/applications). When registering your app
be sure to add the redirect url i.e.
https://app-name.herokuapp.com/complete/coinbase/. Then `export` the following
configuration variables and create the database:

```bash
cd profbit

export SECRET_KEY="super-secret-key"
export SOCIAL_AUTH_COINBASE_KEY="coinbase-key"
export SOCIAL_AUTH_COINBASE_SECRET="coinbase-secret"
export FLASK_APP=app.py

flask syncdb
```
