**Note:** :construction: work in progress

# c8y-bpl

c8y-cli extension to handle tasks for build pipeline

Checkout the [go-c8y-cli extension docs](https://feat-extensions-manager--goc8ycli.netlify.app/docs/tutorials/extensions/creating-an-extension/) for detailed instruction.
Checkout the [Official Cumulocity API Documentation](https://cumulocity.com/api/oee/#operation/getProductionPlanList) for more details.

## What is included?

|Type|Included|Notes|
|----|:-:|-----|
|Aliases|🔲||
|Commands|✅|OEE commands to manage and view profiles and plant data|
|Templates|✅|OEE specific templates|
|Views|✅|Custom OEE views|

## Pre-requisite

:rotating_light: Warning :rotating_light:

This extension relies on an up-coming go-c8y-cli [extensions](https://github.com/reubenmiller/go-c8y-cli/blob/feat/extensions-manager/docs/go-c8y-cli/docs/concepts/extensions.md) feature which has not been officially released yet, so in order to try it out you will have to install the pre-release version via the following instructions.

**Note:** Building `go-c8y-cli` requires go version ≥ 1.20.

### Shell (bash/zsh/fish)
Checkout the [go-c8y-cli extension docs](https://feat-extensions-manager--goc8ycli.netlify.app/docs/tutorials/extensions/creating-an-extension/) for the latest version update

```sh
go install github.com/reubenmiller/go-c8y-cli/v2/cmd/c8y@d6ebaddfd3182f657bf9ad37282f5ad1c25255b3

# Add the go bin folder to your path variable (ideally add this to your shell profile (.zshrc for zsh or .bashrc for bash)
export PATH="$(go env GOPATH)/bin:$PATH"
```

### PowerShell

```powershell
go install github.com/reubenmiller/go-c8y-cli/v2/cmd/c8y@d6ebaddfd3182f657bf9ad37282f5ad1c25255b3

# Add the go bin folder to the path variable and set a powershell alias to it
if ($IsWindows) {
    $env:PATH = "$(go env GOPATH)/bin" + ";" + $env:PATH
    Set-Alias c8y "$(go env GOPATH)/bin/c8y.exe"
} else {
    $env:PATH = "$(go env GOPATH)/bin" + ":" + $env:PATH
    Set-Alias c8y "$(go env GOPATH)/bin/c8y"
}
```

### Post-installation verification

Once you have installed the pre-release version of **go-c8y-cli**, you can confirm that you have the correct version by running the following command:

```sh
c8y version
```

The version suffix should be the first part of the git commit id from the `go install` command, for example:

```sh
| branch         | version                                    |
|----------------|--------------------------------------------|
| (unknown)      | v2.22.5-0.20230504202920-e25a3b0ba9b9      |
```

## Install

The extension can be installed using the following command.

```sh
c8y extension install reubenmiller/c8y-oee

# List the available commands
c8y oee
```
