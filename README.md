# Github Trigger CI Action

Purges the helix pages cache on push.

## Inputs

### `repo-token`

**Required** A github token to issue the dummy commit.

### `helix_url`

**Optional** Base url of the helix pages instance. Uses `ref--repo--owner.hlx.page` by default.

## Example usage

```
on: push

jobs:
  ci_trigger:
    runs-on: ubuntu-latest
    name: Clear helix pages cache
    steps:
      - name: Trigger
        id: trigger
        uses: adobe-rnd/github-purge-cache-action
        with:
          repo-token: ${{ secrets.MY_GITHUB_TOKEN }}
```

# Development

Please run the build script before release to regenerate dist/index.html

```sh-session
$ npm run build
$ git commit -am "..."
$ git push
