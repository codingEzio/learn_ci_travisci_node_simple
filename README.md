### Why

- For fun
- Tutorial link: [A quick Travis CI (Continuous Integration) Tutorial for Node.js developers <small>(on github)</small>](https://github.com/dwyl/learn-travis)

### Issues

- If I'm using `const` and _jshint_ for testing at the same time

  > see [https://stackoverflow.com/a/37472928](https://stackoverflow.com/a/37472928)<br>
  > basically, you just need to add a `.jshintrc` file, then add `{ "esversion": 6 }`

### Actual notes

- Do notice that
  - [_travis-ci.com_](https://travis-ci.com) and [_travis-ci.org_](https://travis-ci.org) are _not_ the same thing (_private_ | _public_)
  - so, for some specific stuff you might need to do in a bit different way, e.g. `travis encrypt` when adding env vars
- Three ways to add _Environment Variables_ <small>(dangerous -> kinda safe -> safe)</small>
  1. whatever: directly add those to `.travis.yml`
  2. travis web interface: something like [https://travis-ci.com/USER/REPO_NAME/settings](#)
  3. encrypt the keys by yourself <small>(I havn't try this in my local machine)</small>
  ```bash
  # 1. you need to get 'ruby' installed in your machine
  # 2. install a library for encrypting the keys
  gem install travis
  # 3.1 encrypt it -> then add to 'secure: GENERATED_STUFF'
  travis encrypt SOMEVAR="secretvalue" --add env.global
  # 3.2 encrypt it -> then add to 'secure: GENERATED_STUFF'
  travis login --pro
  travis encrypt SOMEVAR="secretvalue" --add
  ```

### More

### Links related to _CircleCI_

- [Travis CI <small>(public repo)</small>](https://travis-ci.org/)
- [Travis CI <small>(private repo)</small>](https://travis-ci.com/)
- [Travis doc - Encrypting Keys #usage](https://docs.travis-ci.com/user/encryption-keys#usage)
- [Travis doc - Encrypting Environment Variables](https://docs.travis-ci.com/user/environment-variables/#encrypting-environment-variables)
