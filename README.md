# github-scanner-local

Locally scan all the repositories of a github organization.

## Setup

- Clone below repositories as same location as github-scanner-local
  - [gh-crawl](https://github.com/arshadkazmi42/gh-crawl) 
  - [bash-scripts](https://github.com/arshadkazmi42/bash-scripts)

- Install `[npm-name](https://github.com/sindresorhus/npm-name)` globally 

## Usage

```
sh run.sh {GITHUB_ORGANIZATION_NAME}
```

## Working

#### `run.sh` 
  
Uses `clone.sh`, `grepURL.sh` and `broken.sh`

#### `clone.sh`

Clones all the repositories of the organanization (Note: It does not clones `archived` repositories)

#### `grepURL.sh`

Find all the urls from all the repositories of the organization (Searches in the cloned folder) and stores in results directory

#### `broken.sh`

Checks all the urls found by `grepURL.sh` and captures the status code of the URL


## Commands

- Search for string in all cloned repositories

```
ls -d -1 target/* | grep -v target.txt | xargs -I {} sh search.sh {} "{{STRING_TO_SEARCH}}"
```

```
grep -r -o "{{STRING_TO_SEARCH}}" target/.
```
