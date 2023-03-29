# @guardian/actions-s3

A simple action to support S3 deployments via Riffraff. This is useful when you
have simple requirements and want to avoid manual uploads.

`bucketSsmKey` can be used to customise the target bucket; it defaults to
`/account/services/artifact.bucket`.

`cacheControl` can be used to customise the Riffraff cache control setting.

Example usage:

```yaml
- uses: guardian/actions-s3@v1
  with:
    app: example
    stack: some-stack
    contentDirectory: my-assets-dir
    # Override the below if required:
    # allowedStages: '["CODE", "PROD"]'
    # cacheControl: no-store
    # bucketSsmKey: /account/services/artifact.bucket
    guActionsRiffRaffRoleArn: ${{ secrets.GU_RIFF_RAFF_ROLE_ARN }}
```

**Manual uploads should be avoided for critical infrastructure!**
