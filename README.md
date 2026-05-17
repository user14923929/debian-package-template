# Debian Package Template

A minimal, reusable template for building Debian (.deb) packages.

## Purpose

This repository provides a lightweight starting point to create Debian packages with a predictable layout and basic build helpers.

## Prerequisites

- Debian-based system (Debian, Ubuntu, etc.)
- dpkg-deb, fakeroot, debhelper (apt-get install dpkg-dev debhelper fakeroot)

## Repository layout

- DEBIAN/ - packaging metadata (control, rules, changelog, etc.)

Adjust paths and files under DEBIAN/ to match your package's needs.

## Quick build

1. Populate src/ with your project files (or upstream tarball).
2. Update debian/control, debian/changelog and other metadata.
3. From repository root run:

	fakeroot dpkg-deb --build . build/<package-name>.deb

Or use debuild:

	debuild -us -uc

## Testing

Install the generated package locally:

	sudo dpkg -i build/<package-name>.deb

Resolve missing dependencies with:

	sudo apt-get install -f

## Contributing

Fork and submit pull requests. Keep packaging changes minimal and documented in debian/changelog.

## License

Specify the license for your packaged software and the packaging files (e.g., MIT, GPL-3.0+).
