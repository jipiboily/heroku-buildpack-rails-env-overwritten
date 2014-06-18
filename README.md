# RACK_ENV + RAILS_ENV overriding issue app

This app is to help reproduce an issue in Heroku Ruby build pack overwriting RACK_ENV and RAILS_ENV.

## Steps to reproduce
1. `git clone git@github.com:jipiboily/heroku-buildpack-rails-env-overwritten.git`
- cd in the directory: `cd heroku-buildpack-rails-env-overwritten`
- Create a Heroku app: `heroku create`
- Set RACK_ENV and RAILS_ENV: `heroku config:set RACK_ENV=custom RAILS_ENV=custom`
- `git push heroku`
- wait...
- :boom:, RACK_ENV and RAILS_ENV are now set to production

It looks like it is only for the first build