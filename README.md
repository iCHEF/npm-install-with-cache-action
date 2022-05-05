# npm-install-with-cache-action

## Usage

1. use `actions/checkout` to checkout your repo under `$GITHUB_WORKSPACE`
2. use `actions/setup-node` with node-version
3. use `iCHEF/npm-install-with-cache-action` with inputs if needed

### Inputs

- `npm-token` - defaults to `''`, set auth token if your project dependency contains private packages
- `is-monorepo` - defaults to `false`, set it to true if using action in a monorepo
- `skip-cache` - defaults to `false`, set it to true if wanna skip cache steps

```yml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v1
    - uses: actions/setup-node@v1
      with:
        node-version: '12.x'
    - name: Install packages with cache
      uses: iCHEF/npm-install-with-cache-action@v1
      with:
        npm-token: ${{ secrets.NPM_TOKEN }}
        is-monorepo: true
```
