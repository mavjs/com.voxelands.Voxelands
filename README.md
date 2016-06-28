# Voxelands build files for [flatpak](http://flatpak.org/)

## Create a Voxelands bundle
Check available [runtimes](http://flatpak.org/runtimes.html)
```bash
# Install Freedesktop runtime and SDK
wget https://sdk.gnome.org/keys/gnome-sdk.gpg
flatpak --user remote-add gnome-sdk --gpg-import=gnome-sdk.gpg http://sdk.gnome.org/repo/
flatpak --user install gnome-sdk org.freedesktop.Platform 1.4
flatpak --user install gnome-sdk org.freedesktop.Sdk 1.4

# Build repository with Freedesktop runtime and Voxelands app
flatpak-builder --force-clean --repo=voxelands.com app com.voxelands.Voxelands.json
```

## Install and run Voxelands bundle
```
flatpak --user remote-add --no-gpg-verify --if-not-exists voxelands voxelands.com
flatpak --user install voxelands com.voxelands.Voxelands
flatpak run com.voxelands.Voxelands
```

## Notes
Currently does not work with Nvidia GPUs. (see [flatpak issue](https://github.com/flatpak/flatpak/issues/138))
