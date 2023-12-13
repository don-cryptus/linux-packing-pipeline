# DEB Converter

## Introduction

DEB Converter is a powerful tool designed for converting `.deb` packages into formats suitable for Arch Linux (`.pkg.tar.zst`) and Red Hat Enterprise Linux (RHEL) distributions (`.rpm`). This utility simplifies the process of making Debian packages available to a broader range of Linux users, ensuring compatibility and ease of installation across different Linux environments.

## Features

- **Debian to Arch Conversion**: Convert `.deb` packages to Arch Linux's package format.
- **Debian to RHEL Conversion**: Transform `.deb` packages into RPM format for use in RHEL and its derivatives.
- **Automated Workflow**: Utilizes GitHub Actions to automate the conversion and packaging processes.
- **Checksum Generation**: Ensures integrity of the converted packages by generating MD5 checksums.

## Prerequisites

Before using DEB Converter, ensure that you have a `.deb` package file ready for conversion. and change the variables in the workflow

[real example (rust tauri)](https://github.com/don-cryptus/clippy)


Buildroot: /home/don/rpmbuild/clippy-1.2.2
Name: clippy
Version: 1.2.2
Release: 2
Summary: Clipboard Manager built with Rust & Typescript
License: see /usr/share/doc/clippy/copyright
Distribution: Debian
Group: Converted/unknown
Requires: javascriptcoregtk4.0, webkit2gtk4.0, libxdo, libappindicator-gtk3, xdotool

%define _rpmdir ../
%define _rpmfilename %%{NAME}-%%{VERSION}-%%{RELEASE}.%%{ARCH}.rpm
%define _unpackaged_files_terminate_build 0

%install
mkdir -p %{buildroot}/usr
cp -a %{_topdir}/clippy-1.2.2/usr/* %{buildroot}/usr/

%description
(none)


(Converted from a deb package by alien version 8.95.)

%files
/usr/bin/clippy
/usr/share/applications/clippy.desktop
/usr/share/icons/hicolor/32x32/apps/clippy.png
/usr/share/icons/hicolor/128x128/apps/clippy.png
/usr/share/icons/hicolor/256x256@2/apps/clippy.png
