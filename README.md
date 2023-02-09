# Github Action to OTLP

*NOTE: This is still work in progress*

This action outputs Github Action workflows and jobs details to OTLP via gRPC.

## Inputs

## `endpoint`

**Required** The OTLP endpoint which will receive the data.

## `headers`

**Optional** Additional header configuration to pass in as metadata to the gRPC connection.

## `repo-token`

**Optional** Token to use to authorize access to private repositories. Typically the `GITHUB_TOKEN` secret, with `checks:read` access.

## `tls_disabled`

**Optional** Set to true when sending data to endpoints that are not secured by TLS

## Example usage

```
uses: codeboten/github-action-to-otlp@v1
with:
  endpoint: 'grpc.otlpendpoint.io:443'
```

## Example usage in a private repository

```
uses: codeboten/github-action-to-otlp@v1
with:
  endpoint: 'grpc.otlpendpoint.io:443'
  repo-token: ${{ secrets.GITHUB_TOKEN }}
  tls_disabled: true
```
