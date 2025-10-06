# Scripts

A small collection of Bash scripts that live in my `$PATH`.

Comes with absolutely no guarantees or warranties, but I try to document as much
as I can. Feel free to write issues or make pull requests.

Here's a brief explanation of what they do:

<!-- markdownlint-disable -->
<details>
  <summary>
	<b>battery-pretty</b>
  </summary>

Prints the current battery status in a `$ICON$PERCENTAGE%` format.

Example outputs:

- ` 65%` when charging,
- `󰁹 98%`,
- `󰁾 58%`,
- `󰁻 24%`.

[source](./battery-pretty)

</details>

<details>
  <summary>
	<b>colorpicker</b>
  </summary>

A [hyprpicker](https://github.com/hyprwm/hyprpicker) wrapper that:

- Disables colored output.
- Removes the prefixed `#` (from the hex format).
- Removes the suffixed `\n`.
- Copy the resulting string to the clipboard using
  [wl-copy](https://github.com/bugaevc/wl-clipboard).

An example output would be: `282A36`.

[source](./colorpicker)

</details>

<details>
  <summary>
	<b>new</b>
  </summary>

A [cp](https://man.archlinux.org/man/cp.1) wrapper for code templates.

In the context of this script, a code template - or simply template - is a
directory with the skeleton of a project. For example, a simple c template could
be a directory called "simple_c" that contains a `src/main.c` and a `Makefile`.

The templates live in a "template directory", which defaults to
`$XDG_DATA_HOME/templates` but gets overrided by the `TEMPLATES_DIR` variable.

You can find some templates [here](https://github.com/wedns/templates).

Example Usage:

```bash
# Copy the `simple_c` template to the current directory, with the name
# "simple_c".
new simple_c .
```

```bash
# Copy the `riscv` template to the current directory, with the name "foobar".
new riscv foobar
```

```bash
# Copy the `ruby` template to `/foo/bar`.
new ruby /foo/bar
```

```bash
# Copy the `c_raylib` template to the current directory, with the name "game" 
# and initializes a git directory inside it.
new -g c_raylib game
```

[source](./new)

</details>

<details>
  <summary>
	<b>valgrind-delete-vgcore</b>
  </summary>

A [valgrind](https://valgrind.org/) wrapper that removes all `vgcore.*` files
after execution. The wrapper also propagates the exit status from valgrind.

A `VALGRIND_BIN` variable might be set to define a custom binary for valgrind.

[source](./valgrind-delete-vgcore)

</details>
