# Kustomize plugins
Kustomize allows you to add [plugins](https://kubectl.docs.kubernetes.io/guides/extending_kustomize/), but it isn't super obvious how to do it. This little repo tries to explain at least the basics which I had a lot of trouble figuring out.

# Install
We need to install plugins in the default plugin directory for kustomize. The docs tells us that this location is `$XDG_CONFIG_HOME/kustomize/plugin`, where `$XDG_CONFIG_HOME` by default points to `$HOME/.config`.

So to install the plugin: clone this repo, open a shell in the repo root and run:

`cp -pr plugin/myteam ~/.config/kustomize/plugin`

# Running
To run kustomize with a plugin, we need to also pass the `--enable-alpha-plugins` flag. So to execute the kustomize build here, we'd run:

`kustomize build --enable-alpha-plugins kustomize/base`