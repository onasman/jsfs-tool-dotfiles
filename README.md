# jsfullstackdev-dotfiles
With these files and scripts we have configured the development machines we are using in the FullStack Javascript developer course

All your computers has been preconfigured by running the bootstrapping scripts as described below. Feel free to tweak them to your liking.

## How to's

### Applying to a computer for the first time

1. Open the Terminal
1. Go to the root folder => `cd ~`
1. Clone this repo into the `.dotfiles`-directory => `git clone https://github.com/saltsthlm/jsfullstackdev-dotfiles.git .dotfiles`
1. Go into the directory => `cd .dotfiles`
1. Run the bootstrapping script => `bash script/bootstrap`
1. Stay around for a few minutes, because there will be some questions early in the process
1. After the whole thing starts to crunch away - go get a coffee and read a book. There's a **lot** to download.
1. When everything is done - install [Oh My Zsh](http://ohmyz.sh/) => `sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`
1. Restart you computer

Or do it in a single chain:

```bash
sudo softwareupdate -i -a &&
git clone https://github.com/saltsthlm/jsfullstackdev-dotfiles.git ~/.dotfiles &&
bash ~/.dotfiles/script/bootstrap &&
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

### Keeping your computer updated

Things change. Often and fast. Every so often you would like to run the `dot` command that ensures that everything is up to date. I do this bi-weekly.

Sometimes I feel the need to clean up the cache that Homebrew is using and then there's a handy script (`cleanupHomeBrew.sh`) that does just that. Run it bi-monthly with `bash script/cleanupHomeBrew.sh`.

## About this repo

Stole this part from an [excellent description here](https://github.com/michaelmior/dotfiles)

### Topical

Everything's built around topic areas. If you're adding a new area to your forked dotfiles — say, "Java" — you can simply add a java directory and put files in there. Anything with an extension of .zsh will get automatically included into your shell. Anything with an extension of .symlink will get symlinked without extension into $HOME when you run script/bootstrap.

### What's inside

A lot of stuff. Seriously, a lot of stuff. Check them out in the file browser above and see what components may mesh up with you. Fork it, remove what you don't use, and build on what you do use.

### Components

There's a few special files in the hierarchy.

* `bin/`: Anything in bin/ will get added to your `$PATH` and be made available everywhere.
* `topic/*.zsh`: Any files ending in `.zsh` get loaded into your environment.
* `topic/path.zsh`: Any file named path.zsh is loaded first and is expected to setup $PATH or similar.
* `topic/completion.zsh`: Any file named completion.zsh is loaded last and is expected to setup autocomplete.
* `topic/*.symlink`: Any files ending in `*.symlink` get symlinked into your `$HOME`. This is so you can keep all of those versioned in your dotfiles but still keep those autoloaded files in your home directory. These get symlinked in when you run `script/bootstrap`.
