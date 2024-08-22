# First Debian package

### Installing packages

```
sudo apt install dpkg-dev devscripts debhelper build-essential
```

### Setting up directory structure

```
pakage-name/
|- DEBIAN
   |- control
|- usr
   |- bin
      |- bashscript.sh
```

### Add the following in `control` file

```
Package: package-name
Version: 1.0
Section: base
Priority: optional
Architecture: all
Depends: bash (or other dependencies)
Maintainer: Your Name <your.email@example.com>
Description: A simple package for demonstration purposes
```

### Set Permissions

```
chmod 755 usr/bin/bashscript.sh
chmod 755 DEBIAN
```

### Build Package

Go to the root of package directory and build the package

```
dpkg-deb --build package-name
```

This creates a `.deb` file in the current directory named `package-name.deb`

### Install and Test the package

```
sudo dpkg -i package-name.deb
```

Run the installed script

```
bashscript.sh
```
