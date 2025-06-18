# @arkts/sdk-downloader

Simple function to download the ArkTS SDK, streaming, simple, easy to use, and support resume download, fast ⚡️

## Features 🚀

- ↩️ Resume download ✅
- ⬇ Download Progress, tar extract progress and zip extract progress tracking ✅
- 🧵 HTTP/HTTPS support ✅
- 🔗 Support cancel download ✅
- 🧹 Clean the cache directory after the download is complete ✨
- 👂 Support listen events when download, tar extract and zip extract
- ㊙️ Check the SHA256 of the downloaded `tar.gz` file

## Supported Platforms 💻

- [x] Windows
- [x] macOS
- [x] Linux

The unit test is run on Windows, macOS and Linux, you can see the test results in github actions:

> Current Test Status: [![CI](https://github.com/Groupguanfang/arkts-sdk-downloader/actions/workflows/ci.yml/badge.svg)](https://github.com/Groupguanfang/arkts-sdk-downloader/actions/workflows/ci.yml)

## Install 📦

```bash
pnpm add @arkts/sdk-downloader
```

## Usage 🚀

```ts
import { createDownloader } from '@arkts/sdk-downloader'

const downloader = await createDownloader({
  url: {
    os: SdkOS.MacOS,
    version: SdkVersion.API15,
    arch: SdkArch.ARM,
  },
  cacheDir: 'target/.cache',
  targetDir: 'target',
  resumeDownload: true,
})

await downloader.startDownload(/** Override request options */)
await downloader.checkSha256()
await downloader.extractTar()
await downloader.extractZip()
await downloader.clean()
```

## Author 🤝

- [Naily Zero](https://github.com/groupguanfang)
- QQ: 1203970284
- Email: zero@naily.cc
- WeChat: gcz-zero

## License 📄

MIT
