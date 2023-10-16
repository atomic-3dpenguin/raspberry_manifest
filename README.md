# raspberry_manifest
Manifest file for yocto build of raspberry pi 3b

# Create Directory
```
mkdir ~/pi-yocto && cd ~/pi-yocto
```

# Initialize Repo
```
repo init -u https://github.com/atomic-3dpenguin/raspberry_manifest.git -b mickledore -m yocto-pi.xml

repo sync
```

# Source environment
```
source sources/pokey/oe-init-build-env build
```

# Add Layers
```
bitbake-layers add-layer ../sources/meta-openembedded/meta-oe
bitbake-layers add-layer ../sources/meta-openembedded/meta-python
bitbake-layers add-layer ../sources/meta-openembedded/meta-multimedia
bitbake-layers add-layer ../sources/meta-openembedded/meta-networking
bitbake-layers add-layer ../sources/meta-raspberrypi
bitbake-layers add-layer ../sources/meta-pi
```

# Bitbake
```
bitbake pi-image-base
```