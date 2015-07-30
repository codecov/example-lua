Codecov Lua Example
=====================

| [https://codecov.io][1] | [@codecov][2] | [hello@codecov.io][3] |
| ----------------------- | ------------- | --------------------- |

This repository serves as an **example** on how to use [Codecov Global][4] for
Lua.

## Basic Usage

Run your tests with [LuaCov][5] in order to create the necessary coverage
reports. For example:

```
lua -lluacov awesome-tests.lua
```

After you've run the tests and created a LuaCov report, you can use [Codecov
Global][4] to upload that report to Codecov. See below for more detail.

## [![travis-org](https://avatars2.githubusercontent.com/u/639823?v=2&s=50)](https://travis-ci.org) Travis CI

### Public Repos

Adjust the example in [lua-travis-example][6] to install any necessary
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

+ Add `CODECOV_TOKEN=<your repo token>` to your CI's environment variables.
  (Don't store the raw token in your repo.)
+ Adjust the materials in [lua-travis-example][6] as necessary to work with
  your CI. (See for example: [this post][7] for an example using
  [Drone.io][8].)
+ Run `bash <(curl -s https://codecov.io/bash)` after tests complete.

View source and learn more about [Codecov Global Uploader][4]

[1]: https://codecov.io
[2]: https://twitter.com/codecov
[3]: mailto:hello@codecov.io
[4]: https://github.com/codecov/codecov-bash
[5]: http://keplerproject.github.io/luacov
[6]: https://github.com/moteus/lua-travis-example
[7]: http://ithaca.arpinum.org/2015/07/14/lua-bitbucket-ci-droneio.html
[8]: https://drone.io
