# A fork from [alrra](https://github.com/alrra)’s dotfiles

These are the base dotfiles that I start with when I set up a
new environment.
For more specific local needs I use the `.local`
files described in the [`Local Settings`](#local-settings) section.


## Setup

To setup the dotfiles just run the appropriate snippet in the
terminal:

(:warning: **DO NOT** run the setup snippet if you don't fully
understand [what it does](dotfiles). Seriously, **DON'T**!)

| OS | Snippet |
|:---:|:---|
| Ubuntu | `bash -c "$(wget -qO - https://raw.github.com/zedrix/dotfiles/master/dotfiles)"` |

That's it! :sparkles:

The setup process will:

* Download the dotfiles on your computer (by default it will suggest
  `~/projects/dotfiles`)
* Create some additional [directories](os/create_directories.sh)
* [Symlink](os/create_symbolic_links.sh) the
  [git](git),
  [shell](shell), and
  [vim](vim) files
* Install applications / command-line tools for
  [Ubuntu](os/ubuntu/installs/main.sh)
* Set custom
  [Ubuntu](os/ubuntu/preferences/main.sh) preferences
* Install [vim plugins](vim/vim/plugins)

<table>
    <tbody>
        <tr><td colspan="1">Setup process in action</tr></td>
        <tr>
            <td>
                <img src="https://cloud.githubusercontent.com/assets/1223565/10560844/c580ee18-751f-11e5-8b15-2b8214bacdfd.gif" alt="Setup process on Ubuntu" width="100%">
            </td>
        </tr>
    </tbody>
</table>


## Screenshots


##### Git

<table>
    <tbody>
        <tr><td colspan="1">Output for Git status</tr></td>
        <tr>
            <td>
                <img src="https://cloud.githubusercontent.com/assets/1223565/8397636/3708d218-1ddb-11e5-9d40-21c6871271b9.png" alt="Output for Git status on Ubuntu" width="100%">
            </td>
        </tr>
    </tbody>
</table>

<table>
    <tbody>
        <tr><td colspan="1">Output for Git log</tr></td>
        <tr>
            <td>
                <img src="https://cloud.githubusercontent.com/assets/1223565/10560955/4b5e1300-7523-11e5-9e96-95ea67de9474.png" alt="Output for Git log on Ubuntu" width="100%">
            </td>
        </tr>
    </tbody>
</table>


##### tmux + vim

<table>
    <tbody>
        <tr>
            <td>
                <img src="https://cloud.githubusercontent.com/assets/1223565/10560956/557ca2de-7523-11e5-9000-fc1e189a95f5.png" alt="tmux and vim on Ubuntu" width="100%">
            </td>
        </tr>
    </tbody>
</table>


## Customize

### Local Settings

The dotfiles can be easily extended to suit additional local
requirements by using the following files:

#### `~/.bash.local`

If the `~/.bash.local` file exists, it will be automatically sourced
after all the other [bash related files](shell), thus, allowing its
content to add to or overwrite the existing aliases, settings, PATH,
etc.

Here is a very simple example of a `~/.bash.local` file:

```bash

#!/bin/bash

# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

# Set local aliases

alias starwars="telnet towel.blinkenlights.nl"

# - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

# Set PATH additions

PATH="/usr/local/bin:$PATH"
PATH="$PATH:$HOME/projects/dotfiles/bin"

export PATH

```

#### `~/.gitconfig.local`

If the `~/.gitconfig.local` file exists, it will be automatically
included after the configurations from `~/.gitconfig`, thus, allowing
its content to overwrite or add to the existing `git` configurations.

__Note:__ Use `~/.gitconfig.local` to store sensitive information such
as the `git` user credentials, e.g.:

```bash
[user]
    name = zedrix
    email = zedrix@example.com
```

#### `~/.vimrc.local`

If the `~/.vimrc.local` file exists, it will be automatically sourced
after `~/.vimrc`, thus, allowing its content to add or overwrite the
settings from `~/.vimrc`.

#### `~/.gvimrc.local`

Same as `~/.vimrc.local` but for `~/.gvimrc`.


## Update

To update the dotfiles you can either run the [`dotfiles`
script](dotfiles) or, if you want to just update one particular part,
run the appropriate [`os` script](os).


## Acknowledgements

Inspiration and code was taken from many sources, including:

* [Mathias Bynens'](https://github.com/mathiasbynens)
  [dotfiles](https://github.com/mathiasbynens/dotfiles)


## License

The code is available under the [MIT license](LICENSE.txt).
