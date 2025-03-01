# ARCHIVED! Development of this boxkit has moved to [dev-boxkits](https://github.com/ngraham20/dev-boxkits)
# rusty-boxkit
## Features
### Rust development tools
- rust

### VS Code Extensions
By default, this image comes with three VS Code extensions, which can be modified by changing `post-install/vscode-extensions.list`
- Night Owl (my dark theme of choice)
- rust-analyzer (for Rust)

These extensions are installed to `$HOME/.vscode-extensions`, which keeps them separate from any other boxes you might spin up. This means your extensions can be unique to the dev environment you use the dev box for.

### 1Password ssh-enabled
The post-installation justfile creates a symlink to `$DISTROBOX_HOST_HOME/.1Password` to allow 1Password ssh keys to be usable inside the distrobox. A symlink to `.gitconfig` and a copied `.ssh/config` are also included to facilitate this.

## For use in Distrobox
This boxkit is designed for use in Distrobox with a modified `HOME` directory. As such, a `justfile` is included in `/opt/post-install` to complete the installation.

Upon loading into the distrobox, do the following:
```bash
$ just -f /opt/post-install/justfile
$ freload # custom fish function reloads the fish config
```
