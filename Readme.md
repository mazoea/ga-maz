# Github Actions action repository

Use e.g.,:

```
      - uses: mazoea/ga-maz/start@master
        with:
          UID: ${{ needs.configure.outputs.uid }}
          GID: ${{ needs.configure.outputs.gid }}
```
