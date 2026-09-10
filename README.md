# dsh-s3

S3-compatible bucket browser for [DeepSeek Harness](https://github.com/deepseek-ai/deepseek-harness) (`dsh`). Adds an "S3" entry to the web GUI sidebar: configure bucket connections (bucket, endpoint, region, access keys, path-style, optional prefix), browse / upload / download / preview / rename / delete objects, create presigned share links — and a single switch that injects the `s3_*` toolset into the agent (`s3_buckets`, `s3_list`, `s3_stat`, `s3_get`, `s3_put`, `s3_upload`, `s3_download`, `s3_copy`, `s3_presign`, `s3_mkdir`, `s3_delete`).

Works with AWS S3, MinIO, Alibaba OSS, Tencent COS, Cloudflare R2, Backblaze B2 and any other S3-compatible endpoint. The AWS SDK is bundled, so the package has no runtime dependencies.

```sh
dsh plugin --profile web add dsh-s3
# or, from a packed tarball downloaded from the Releases page:
dsh plugin --profile web add file:./dsh-s3-<version>.tgz
```

Prebuilt tarballs are attached to every [GitHub Release](https://github.com/Onenightcarnival/dsh-s3/releases); each `vX.Y.Z` tag is built and published automatically by CI.

Credentials live in `~/.dsh/dsh-s3.json` (mode 0600) and never reach the browser or the agent. Routes are loopback-only and require the GUI's browser-session cookie. See [README.zh.md](README.zh.md) for the full guide (Chinese).

MIT
