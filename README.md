# Mesonic: A Vim plugin for Meson build system

Mesonic is a plugin that uses Vim compiler infrastructure to integrate Meson
build system into an editor with special handling of out-of-source builds. It
sets 'makeprg', 'errorformat' options and provides syntax highlighting for
``meson.build`` files.

## Usage

Use ``:MesonInit`` to initialise build directory for the first time. After that
you can issue ``:make`` command as usual, which produces correct quickfix list
no matter what current directory is. All commands work as expected from any
subdirectory of your project.

You can customise meson and ninja commands with the following variables, which
can be either global or buffer local. Defaults are listed below.

	let b:meson_command = 'meson'
	let b:meson_ninja_command = 'ninja'        " ninja-build on Fedora 23

If you want to switch between build directories, issue ``:MesonInit`` command with an
argument. For example, to switch to 'build-special' directory, issue

	:MesonInit 'build-special'

The directory will be initialised if it does not exist or does not contain
``build.ninja`` file. As of the current version Meson options can be added only via
``b:meson_command`` variable.

## Limitations

Mesonic assumes that build directory is a subdirectory of top-level directory of
your project, i.e. build directory is located in the same directory where your
main ``meson.build`` file is. In all other cases it may produce wrong file paths
in quickfix list.

## Contributing

This plugin was created as a result of my passion for Vim and C++
programming, and as a consequence of reading
["Learn Vimscript the Hard Way"](http://learnvimscriptthehardway.stevelosh.com/)
by Steve Losh. Feel free to contribute or post a bug at GitHub project page
(here).

## License

Mesonic is GPL licensed.
