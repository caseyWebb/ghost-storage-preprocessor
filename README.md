# Ghost Storage Preprocessor

> Preprocess uploads to [Ghost][]

This module must be used with [ghost-storage-preprocessor transform(s)][] and a [storage adapter][].

**NOTE:** This module is experimental. At the moment, only the default installation using ghost-cli and the below installation is supported.

## Installation

```bash
# Install preprocessor
$ npm install ghost-storage-preprocessor
$ mkdir -p ./content/adapters/storage
$ cp -r ./node_modules/ghost-storage-preprocessor ./content/adapters/storage/preprocessor

# Install preprocessor transform
$ npm install ghost-storage-preprocessor-imagemin
$ mkdir -p ./content/adapters/storage/preprocessor/transforms
$ cp -r ./node_modules/ghost-storage-preprocessor-imagemin ./content/adapters/storage/preprocessor/transforms/imagemin
```

## Configuration

```json
{
  "storage": {
    "active": "preprocessor",
    "preprocessor": {
      // Storage transformer (installed separately)
      "transforms": [
        ["imagemin", { /* imagemin transform opts */ }]
      ],

      // Optional, storage adapter to pass transformed uploads to (installed separately). Defaults to local file system.
      "use": "s3"
    },
    "s3": {
      ...
    }
  }
}
```

[Ghost]: https://ghost.org
[storage adapter]: https://docs.ghost.org/docs/using-a-custom-storage-module