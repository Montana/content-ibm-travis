# Power Build

Adding Power (`ppc64le`) support to a project in Travis is almost as easy as one, two, three. 

First what you'll want to do in the `.travis.yml` file for your project, find the `os: linux` line. This is what tells Travis CI to perform a Linux build. So it would look something like this:

`arch: ppc64le`

This is the `arch` hook, and calls the Power build to Travis CI.

# IBM Z

Now adding `Z` is just as simple, right after `os: linux`, you'll want to add:

`arch: s390x`

Now your Travis CI build is running `IBM Z`. 
