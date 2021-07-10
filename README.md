# Hugh.io 
#name: NPM Publish

on:
  release:
    types: [created]

jobs:

  publish-npm:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-node@v1
        with:
          node-version: 12
          registry-url: https://registry.npmjs.org/
      - run: npm publish
        env:
          NODE_AUTH_TOKEN: ${{secrets.npm_token}}
          echo Add other actions to build,
          echo test, and deploy your project.
1 
