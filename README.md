# hackage-add-repository
Adds a repository to cabal/config


## Usage Examples

A preferred way is to use Hackage token when talking to Hackage from CI:

```
- name: Setup private hackage
  uses: haskell-actions/hackage-add-repository@v1
  with:
    repositoryName: "private"
    repositoryUri: ${{ secrets.HACKAGE_SERVER }}
    authToken: ${{ secrets.HACKAGE_AUTH_TOKEN }}
```

Alternatively, username/password can still be used (although it is a discouraged practice):

```
- name: Setup private hackage
  uses: haskell-actions/hackage-add-repository@v1
  with:
    repositoryName: "private"
    repositoryUri: ${{ secrets.HACKAGE_SERVER }}
    username: ${{ secrets.HACKAGE_USERNAME }}
    password: ${{ secrets.HACKAGE_PASSWORD }}
```

In both cases it is possible to specify `roorKeys` parameter, which is optional but there if required.
