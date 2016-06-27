# Voxelands specification for [flatpak](http://flatpak.org/)

## Create a Voxelands bundle

```bash
# Install GNOME runtime and SDK
wget https://sdk.gnome.org/keys/gnome-sdk.gpg
flatpak --user remote-add gnome-sdk --gpg-import=gnome-sdk.gpg http://sdk.gnome.org/repo/
flatpak --user install gnome-sdk org.gnome.Platform 3.20
flatpak --user install gnome-sdk org.gnome.Sdk 3.20

# Build repository with GNOME runtime and Voxelands app
flatpak-builder --force-clean --repo=voxelands-repo app com.voxelands.Voxelands.json
```

## Install and run Voxelands bundle
```
flatpak --user remote-add --no-gpg-verify --if-not-exists voxelands-repo app 
flatpak --user install voxelands-repo com.voxelands.Voxelands
flatpak run com.voxelands.Voxelands
```
