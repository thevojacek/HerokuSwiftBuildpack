# Heroku Swift Buildpack

This is a simple and straightforward buildpack for Heroku cloud environment to deploy your Swift applications with ease!
This buildpacks automatically installs specified version of Swift and Clang and builds your application for Heroku environment!

## Compatibility

Currently, this buildpack is tested and working on a newest heroku stack, "**heroku-18**", which is based on Ubuntu 18.04. Older stacks probably won't work.

If you need to upgrade your Heroku stack, there is an easy to follow [tutorial](https://devcenter.heroku.com/articles/upgrading-to-the-latest-stack) on Heroku's website.

**It only works with Swift applications, which are using Swift Package Manager.** So your app will be detected and buildpack used only if your app contains **Package.swift** file in it's root directory.

## Usage

### Specify a Swift version
You may, specify a specific release of Swift you want to install by including **.swift-version** file in the home directory of your app. If you don't specify a version, it defaults to the "**4.2.1**" release at the moment.

```shell
$ ls -la
-rw-r--r--@  1 name  staff    41B  6 pro 19:48 .gitignore
-rw-r--r--@  1 name  staff     5B  7 pro 17:14 .swift-version
...

$ cat .swift-version
4.2.1
```

### Procfile
Also, you **must** specify a Procfile for Heroku to determine, which process you want to run. Name of the process should equal to target name specified in your **Package.swift** file.

```shell
$ ls -la
-rw-r--r--@  1 name  staff   681B 10 pro 19:26 Package.swift
-rw-r--r--@  1 name  staff    21B  9 pro 15:25 Procfile
...

$ cat Procfile
web: ./Application
```

### Example usage
**All you need to do is just to add the buildpack to your Heroku application and push a new release like so:**

```shell
$ ls
Procfile Package.swift Sources
...

$ heroku buildpacks:set https://github.com/thevojacek/HerokuSwiftBuildpack.git

$ git push heroku master
...
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