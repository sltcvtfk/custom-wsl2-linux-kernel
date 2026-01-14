# Custom WSL2 Linux Kernel

This repository is forked from the excellent [Custom WSL2 Linux Kernel by LGUG2Z](https://github.com/LGUG2Z/custom-wsl2-linux-kernel).

This project aims to use GitHub Actions Workflows to produce and publish
up-to-date, versioned custom builds of
[WSL2-Linux-Kernel](https://github.com/microsoft/WSL2-Linux-Kernel) with
`DMI_SYSFS` and
`FW_CFG_SYSFS` enabled.

These custom kernels builds can be used to user Roblox Sober on Windows.

The versioning scheme of this project matches the versioning scheme used by
WSL2-Linux-Kernel.

## Usage

- Download the custom kernel from the releases page
- Make sure you have saved all your work in all WSL2 instances
- Shutdown all WSL2 instances with `wsl --shutdown`
- Edit (or create) the ~/.wslconfig file on Windows
- Specify the path to the custom kernel

```ini
# For example...
[wsl2]
kernel=C:\\Users\\YOUR_USERNAME\\Downloads\\vmlinux
```

- Start a WSL2 instance
- Check that the kernel is running with `uname -sr`

```
Linux 5.15.123.1-paname-sober-custom-WSL2
```

## Modification

If you want to build and publish your own custom WSL2 Linux Kernel, you can
fork this repository and make whatever configuration modifications in
[config-wsl](config-wsl). The [GitHub Actions
Workflow](.github/workflows/build.yml) will take care of the rest.

Please take care to update `CONFIG_LOCALVERSION` to distinguish your custom
kernel from this one.
