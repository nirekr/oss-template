# oss-template
[![Build Status](https://img.shields.io/travis/jonathanewerner/oss-template.svg?style=flat-square)](https://travis-ci.org/jonathanewerner/oss-template)
[![Code Coverage](https://img.shields.io/codecov/c/github/jonathanewerner/oss-template.svg?style=flat-square)](https://codecov.io/github/jonathanewerner/oss-template)
[![version](https://img.shields.io/npm/v/oss-template.svg?style=flat-square)](http://npm.im/oss-template)
[![downloads](https://img.shields.io/npm/dm/oss-template.svg?style=flat-square)](http://npm-stat.com/charts.html?package=oss-templateor&from=2015-08-01)
[![MIT License](https://img.shields.io/npm/l/oss-template.svg?style=flat-square)](http://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)
[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg?style=flat-square)](http://commitizen.github.io/cz-cli/)

A template repository for OSS npm packages.

## Usage
```bash
git clone git@github.com:jonathanewerner/oss-template.git
cd oss-template
rm -rf .git
ncu -u # npm install -g npm-check-update before
npm install
npm run validate # check that skeleton code works
```

Then some manual steps:

1. Change package.json `name`, `description`, `keywords`, `repository`.
2. Create new repo for project on github
3. `git init`
4. `git remote add <your-new-repo-origin>`
5. Adapt badge links to repo name
6. `semantic-release-cli setup`
7. Edit `.travis.yml` by adding / changing to the following:

    ```
    before_install:
      - npm i -g npm@^3.0.0
    script:
      - npm run validate
    after_success:
      - npm run report-coverage && npm run semantic-release
    branches:
      only:
        - master
    ```
