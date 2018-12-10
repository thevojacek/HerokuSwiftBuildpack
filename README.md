# Heroku Swift Buildpack

This is a buildpack for Heroku cloud environment to deploy your Swift applications!

## Compatibility

Currently, this buildpack is tested and working on a newest heroku stack, "heroku-18", which is based on Ubuntu 18.04. Older stacks probably won't work.

## Usage
You may, specify a specific release of Swift you want to install by includins .swift-version file in home directory of your app. If you don't specify a version, it defaults to the "4.2.1" release at the moment.

All you need to do is just to add the buildpack to your Heroku application and push a new release like so:

```shell
heroku buildpacks:set https://github.com/thevojacek/HerokuSwiftBuildpack.git
git push heroku master
```