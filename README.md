# Heroku Swift Buildpack

This is a simple and straightforward buildpack for Heroku cloud environment to deploy your Swift applications with ease!

## Compatibility

Currently, this buildpack is tested and working on a newest heroku stack, "**heroku-18**", which is based on Ubuntu 18.04. Older stacks probably won't work.

If you need to upgrade your Heroku stack, there is an easy to follow [tutorial](https://devcenter.heroku.com/articles/upgrading-to-the-latest-stack) on Heroku's website.

## Usage
You may, specify a specific release of Swift you want to install by including **.swift-version** file in the home directory of your app. If you don't specify a version, it defaults to the "**4.2.1**" release at the moment.

```shell
-rw-r--r--@  1 name  staff    41B  6 pro 19:48 .gitignore
-rw-r--r--@  1 name  staff     5B  7 pro 17:14 .swift-version
cat .swift-version
4.2.1
```

All you need to do is just to add the buildpack to your Heroku application and push a new release like so:

```shell
heroku buildpacks:set https://github.com/thevojacek/HerokuSwiftBuildpack.git
git push heroku master
```

## License
MIT License

Copyright (c) 2018 Jan Vojáček

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.