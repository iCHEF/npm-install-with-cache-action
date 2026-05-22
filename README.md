# npm-install-with-cache-action v4

## Usage

1. use `actions/checkout` to checkout your repo under `$GITHUB_WORKSPACE`
2. use `actions/setup-node` with node-version
3. use `iCHEF/npm-install-with-cache-action` with inputs if needed

### Inputs

- `npm-token` - defaults to `""`. Provide auth token if your project dependency contains private packages.
- `skip-cache` - defaults to `"false"`. Set it to `"true"` to skip cache steps.
- `engine` - default to `"npm"`. Also supports `"yarn"`.
- `args` - defaults to `""`, will be passed to package manager when running install.

```yml
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v6
    - uses: actions/setup-node@v6
      with:
        node-version: 26
    - name: Install packages with cache
      uses: iCHEF/npm-install-with-cache-action@v4
      with:
        npm-token: ${{ secrets.NPM_TOKEN }}
        engine: npm
        args: --force
```
