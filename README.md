Codecov Lua Example [![travisCI](https://travis-ci.org/codecov/example-lua.svg)](https://travis-ci.org/codecov/example-lua) [![codecov.io](http://codecov.io/github/codecov/example-lua/branch/master/graphs/badge.svg)](http://codecov.io/github/codecov/example-lua)
=====================

| [https://codecov.io][1] | [@codecov][2] | [hello@codecov.io][3] |
| ----------------------- | ------------- | --------------------- |

This repository serves as an **example** of how to use [the Codecov global
uploader][4] with Lua.

Note that the coverage is deliberately incomplete. (I swear by Kent Beck!) That
way you can [follow the badge link][5] and see how [Codecov][1] works. You can
view the code there, see hits and misses for coverage, etc.

## Basic Usage

Run your tests with [LuaCov][6] in order to create the necessary coverage
reports. For example:

```
lua -lluacov awesome-tests.lua
```

After you've run the tests and created a LuaCov report, you can use [the
Codecov global uploader][4] to push that report to Codecov. See below for
further details.

## [![travis-org](https://avatars2.githubusercontent.com/u/639823?v=2&s=50)](https://travis-ci.org) Travis CI

### Public Repos

Adjust the example in [lua-travis-example][7] to install any necessary
dependencies and test with multiple versions of Lua (if desired).

Then simply add this to `.travis.yml`:

```yml
after_success:
  - bash <(curl -s https://codecov.io/bash)
```

### Private Repos

Add to your `.travis.yml` file.

```yml
env:
  global:
    - CODECOV_TOKEN=:uuid-repo-token

after_success:
  - bash <(curl -s https://codecov.io/bash)
```

## Other CI services

+ Adjust the materials in [lua-travis-example][7] as necessary to work with
  your CI. (See for example: [this post][8] for an example using
  [Drone.io][9].)
+ Add `CODECOV_TOKEN=<your repo token>` to your CI's environment variables.
  (Don't store the raw token in your repo.)
+ Run `bash <(curl -s https://codecov.io/bash)` after tests complete.

## More details

Visit [the global uploader's repo][4] to view its source and learn more about
the script.

[1]: https://codecov.io
[2]: https://twitter.com/codecov
[3]: mailto:hello@codecov.io
[4]: https://github.com/codecov/codecov-bash
[5]: http://codecov.io/github/codecov/example-lua?branch=master
[6]: http://keplerproject.github.io/luacov
[7]: https://github.com/moteus/lua-travis-example
[8]: http://ithaca.arpinum.org/2015/07/14/lua-bitbucket-ci-droneio.html
[9]: https://drone.io
