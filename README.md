# kami-regex-extract

[![KAMI Plugin](https://img.shields.io/badge/KAMI-plugin-8A2BE2)](https://github.com/Hypijump31/KAMI)
[![Signed](https://img.shields.io/badge/Ed25519-signed-green)](https://github.com/Hypijump31/kami-registry)

Extract regex capture groups from text (supports multiple matches).

## Install

```bash
kami install Hypijump31/kami-regex-extract@v0.1.0
```

## Usage

```bash
# Extract emails
kami exec dev.kami.regex-extract '{"pattern": "[\\w.]+@[\\w.]+", "text": "Contact alice@example.com or bob@test.org"}'

# First match only
kami exec dev.kami.regex-extract '{"pattern": "\\d+", "text": "abc 123 def 456", "all": false}'
```

## Arguments

| Name | Type | Required | Description |
|------|------|----------|-------------|
| `pattern` | string | yes | Regular expression (Rust regex syntax) |
| `text` | string | yes | Text to search in |
| `all` | boolean | no | Return all matches (true) or only the first (false). Default: true |

## Build from source

```bash
git clone https://github.com/Hypijump31/kami-regex-extract
cd kami-regex-extract
kami build . --release
```

To also package as plugin.zip:

```bash
kami build . --release --package
```

## Security

- Filesystem: none
- Network: none
- Max memory: 32 MB
- Max execution: 2000 ms

## License

MIT
