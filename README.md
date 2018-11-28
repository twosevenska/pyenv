# Pyenv

## What is this

[pyenv] plugin support for the fish shell.

## Disclaimers

1. This plugin for Fisherman is no longer maintained by the original owner [daenney](https://github.com/daenney/pyenv).
1. I'm currently updating this fork jußst so I can have it work with my setup. It sounds a bit egotistical, but it simply was easier/faster editing this.
1. I'm in no way familiar with the best practices around this, but again, not this is a quick bandage solution for me

## Install

With [fisherman]

```shell
fisher add twosevenska/pyenv
```

## Notes

You need <https://github.com/yyuu/pyenv> to use this plugin.

This plugin replaces what `status --is-interactive; and . (pyenv init -|psub)`
does in a more fishy way. This brings the startup time of your shell down
as we do not generate full completions every time the shell starts but only
when `pyenv` gets called.

On Fish 2.3.0 and later support was introduced that automatically loads
snippets in `conf.d`. However, these snippets are evaluated **before** your
`config.fish`. If you're setting `PYENV_ROOT` in your `config.fish` to
relocate your pyenv installation this will be evaluated after our plugin
gets loaded and hence have no effect. In order to fix this you should drop
a `000-env.fish` file in your `~/.config/fish/conf.d` folder which sets
up your environment accordingly.

[slack-link]: https://fisherman-wharf.herokuapp.com/
[slack-badge]: https://fisherman-wharf.herokuapp.com/badge.svg
[fisherman]: https://github.com/fisherman/fisherman
[pyenv]: https://github.com/yyuu/pyenv
