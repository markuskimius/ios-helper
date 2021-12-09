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

`git clone https://github.com/markuskimius/ios-helper` then put
`ios-helper/bin` in your `PATH`.


## Usage

For the majority of programs normally built with `./configure && make && make
install`, just typing `ios ./configure && make && make install` will build and
install the software for the iOS.  Use `isim` instead of `ios` to build it for
the iOS Simulator.

By default iOS files are installed to `$HOME/ios` and iOS Simulator files to
`$HOME/ios-sim`.  Change it by setting the environment variable `IOS_PREFIX`.
It may also be set by by passing `-p PREFIX` to `ios` _before_ `configure`
which sets the environment variables appropriately and passes `--prefix=PREFIX`
to `configure` automatically.  Other arguments may be passed to `configure`
_after_ `configure`.

As of this writing only one architecture can be targeted per build.  As in, no
universal binaries (for now).  By default iOS targets `arm64`; iOS Simulator
targets the architecture of the Mac under which the script is run.  Change
these defaults by setting the environment variables `IOS_ARCH` and `MAC_ARCH`,
respectively, before running `ios` or `isim`.  The architecture may also be
set by passing `-a ARCH` option before `configure`.


## Examples

See [SDL2-ios].


## License

[Apache 2.0]


[cafe]: <https://github.com/markuskimius/cafe>
[SDL2-ios]: <https://github.com/markuskimius/SDL2-ios>
[Apache 2.0]: <https://github.com/markuskimius/ios-helper/blob/master/LICENSE>
