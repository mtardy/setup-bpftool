# Setup bpftool

This action installs bpftool in your environment for use in actions by
downloading and caching a static version.

## Usage

Using default inputs:

```yaml
steps:
  - name: Checkout code
    uses: actions/checkout@v3

  - name: Install bpftool
    uses: mtardy/setup-bpftool@v1

  - name: Run bash script
    run: |
      # example script using bpftool
      bpftool version
```

Note that you might want to set the `token` variable to avoid rate limiting
from the GitHub API.

Using custom inputs:

```yaml
steps:
  - name: Checkout code
    uses: actions/checkout@v3

  - name: Install bpftool
    uses: mtardy/setup-bpftool@v1
    with:
      version: 'v7.2.0'
      path: '/usr/bin'
      token: ${{ secrets.GITHUB_TOKEN }}

  - name: Run bash script
    run: |
      # example script using bpftool
      bpftool version
```

## Inputs

| Name      | Type   | Default          | Description                                                                                         |
| --------- | ------ | ---------------- | --------------------------------------------------------------------------------------------------- |
| `version` | String | `latest`         | [bpftool](https://github.com/libbpf/bpftool/releases/) version to install. (eg. `v7.2.0`, `latest`) |
| `path`    | String | `/usr/local/bin` | Destination path to install bpftool                                                                 |
| `token`   | String |                  | A GitHub token (e.g. `secrets.GITHUB_TOKEN`) to authenticate requests to GitHub API                  |

## License

[Apache License 2.0](LICENSE)
