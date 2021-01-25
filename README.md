# IBM Power Build

Adding Power (`ppc64le`) support to a project in Travis is almost as easy as one, two, three. 

First what you'll want to do in the `.travis.yml` file for your project, find the `os: linux` line. This is what tells Travis CI to perform a Linux build. So it would look something like this:

`arch: ppc64le`

This is the `arch` hook, and calls the Power build to Travis CI.

# IBM Z

Now adding `Z` is just as simple, right after `os: linux`, you'll want to add:

`arch: s390x`

Now your Travis CI build is running `IBM Z`. So we've attatched an example if we wanted to build a multi arch Travis CI project (both `s390x` and `ppc64`) in C++.

# Travis CI

The `.travis.yml` file is where the set of instructions will go like `os: linux` and definining your architecutre. Here is a sample `.travis,yml` for our `Hello World` C++ project: 

```yaml
os: linux
dist: xenial
language: cpp
compiler: 
  - gcc
  - clang
jobs:
  include:
   - os: linux
     arch: ppc64le
   - os: linux
     arch: s390x
     compiler: gcc
      
script: chmod u+x ./build.sh && ./build.sh
```
As you can see in this build, we are using both `arch` ppc64le, and s390x. We can remove one or another depending on our needs. For your convienence we will link you to the actual project so you can see first hand. The project can be found [here](https://github.com/Montana/cpp-travis-multiarch). 

You can see the build results from travis-ci.com, right [here](https://travis-ci.com/Montana/cpp-travis-multiarch).

# For more information 

For more information, please visit [this](https://github.com/Montana/manifest) helpful repository made by Travis CI for more information on more complex builds when involving IBM Power/Z.
