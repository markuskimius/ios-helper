# ios-helper

Tools to make it easier to port Unix programs to iOS.


## Tools

* ios - Execute a program in an environment for building for the iOS.
* isim - Execute a program in an environment for building for the iOS Simulator.


## Requirements

A Mac!

You're also expected to have some development knowledge, and have Xcode
installed with the command line tools.


## Installation

The easiest way to install ios-helper is to install [cafe] then run `cafe
install-git https://github.com/markuskimius/ios-helper`

Alternatively, `git clone https://github.com/markuskimius/ios-helper` then put
`ios-helper/bin` in your `PATH`.


## Usage

For the majority of programs normally built with `./configure && make && make
install`, just typing `ios configure && make && make install` will build and
install the software for the iOS.  Use `isim` instead of `ios` to build it for
the iOS Simulator.

Note the lack of `./` in front of `configure`; `configure` is an argument to
`ios`, not the path to the configure script.  The `configure` argument expects
the `configure` script to be in the current directory.

By default, iOS files are installed into `$HOME/ios` and iOS Simulator files
are installed into `$HOME/ios-sim`.  This may be changed by passing the `-p
PREFIX` option to `ios` or `isim`, before `configure`.  Forwarding this value
to `configure` as `--prefix=PREFIX` is handled by `ios` or `isim`.  If
additional options need to be passed to `configure`, just pass it after
`configure`, which may be occasionally necessary to build an app for iOS.

As of this writing only one architecture can be targeted per build.  As in, no
universal binaries (for now).  By default iOS targets `arm64`; iOS Simulator
targets the architecture of the Mac under which the script is run.  Set the
environment variables `IOS_ARCH` and `MAC_ARCH`, respectively, before running
`ios` or `isim` to change these defaults.


## Examples

See [SDL2-ios].


## License

[Apache 2.0]


[cafe]: <https://github.com/markuskimius/cafe>
[SDL2-ios]: <https://github.com/markuskimius/SDL2-ios>
[Apache 2.0]: <https://github.com/markuskimius/ios-helper/blob/master/LICENSE>
