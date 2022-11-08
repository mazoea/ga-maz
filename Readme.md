# Github Actions action repository

Use e.g.,:

```
      - uses: mazoea/ga-maz/start@master
        with:
          UID: ${{ needs.configure.outputs.uid }}
          GID: ${{ needs.configure.outputs.gid }}
```

```
      - name: notify MS teams
        uses: mazoea/ga-maz/ms-teams-info@master
        with:
          github-token: ${{ github.token }}
          ms-teams-webhook-uri: ${{ secrets.XXX }}
          notification-color: '28a745'
          notification-summary: '&#x2705 Finished [${{ github.repository }}] [${{ env.JOBNAME }}] by [${{ github.actor }}] on [${{ runner.os }}]'
          notification-failure: '&#x1F621&#x1F621&#x1F621 FAILED [${{ github.repository }}] [${{ env.JOBNAME }}]'
          success: ${{ job.status == 'success' }}
        if: ${{ always() }}
```