### Emacs config to cure my text-editor hopping


# 1

```bash
rm -rf ~/.emacs.d \
       ~/.emacs \
       ~/.emacs~ \
       ~/.config/emacs \
       ~/.config/doom \
       ~/.doom.d \
       ~/.cache/emacs \
       ~/.cache/doom \
       ~/.local/share/emacs \
       ~/.local/state/emacs
```

# 2

```bash
git clone https://github.com/Geordanny1/emacs-kick.git ~/.emacs.d
```

# 3 

```bash
emacs -nw --eval="(ek/first-install)"
```

Both methods will install all necessary packages and apply the
configuration.

**NOTE**: During the initial setup, you'll be prompted to install Tree-sitter
grammars and download some fonts. This configuration uses **Nerd Fonts** by
default, so installing them now is highly recommended for the best experience.

**VERY IMPORTANT**: On first launch, Emacs will also **native compile some
external packages**, which may take a little time. Additionally, the first time
you perform certain actions, like opening the tree explorer, Emacs may compile
related components in the background. This is completely normal and only
happens once per feature. You might notice a brief moment of sluggish
performance during this initial compilation.

3. **Set terminal mode by default**:

**Note on Emacs TUI/GUI**: Emacs automatically adapts to either
graphical or terminal mode depending on the environment. But if
you're in a graphical session and prefer terminal mode, just use:

```bash
emacs -nw
```

To ensure Emacs always opens in terminal mode, add the following to
your `.bashrc` or `.zshrc`:

```bash
alias emacs='emacs -nw'
```

Then, reload your shell configuration with:

```bash
source ~/.bashrc  # for bash
source ~/.zshrc   # for zsh
```

4. **Start Emacs**:

Once set up, start Emacs with:

```bash
emacs
```

**Usage Tips**:

- **Leader Key**: The leader key is set to `SPC` (spacebar),
  `which-key` is there to help you discover keybindings.
- **Help Commands**:
- `SPC h i` opens the Emacs info documentation (`M-x info`).
- `SPC h v` allows you to explore available variables.
- `SPC h f` lets you explore functions.
- `SPC h k` displays keybindings.

**Troubleshooting**:

- If you encounter any issues during installation, check the
  `*Messages*` buffer for more information. You can switch between
  buffers with `SPC SPC`, and navigate options using `C-p` and `C-n`.

## Available Commands

| Keybinding     | Action                                    |
| -------------- | ----------------------------------------- |
| `SPC`          | Leader key                                |
| `TAB`          | Call completion                           |
| `C-d`          | Scroll down                               |
| `C-u`          | Scroll up                                 |
| `<leader> s f` | Find file                                 |
| `<leader> s g` | Grep                                      |
| `<leader> s G` | Git grep                                  |
| `<leader> s r` | Ripgrep                                   |
| `<leader> s h` | Consult info                              |
| `<leader> /`   | Consult line                              |
| `<leader> x x` | Consult Flymake                           |
| `] d`          | Next Flymake error                        |
| `[ d`          | Previous Flymake error                    |
| `<leader> x d` | Dired                                     |
| `<leader> x j` | Dired jump                                |
| `<leader> x f` | Find file                                 |
| `] c`          | Next diff hunk                            |
| `[ c`          | Previous diff hunk                        |
| `<leader> e e` | Toggle NeoTree                            |
| `<leader> g g` | Open Magit status                         |
| `<leader> g l` | Show current log                          |
| `<leader> g d` | Show diff for current file                |
| `<leader> g D` | Show diff for hunk                        |
| `<leader> g b` | Annotate buffer with version control info |
| `] b`          | Switch to next buffer                     |
| `[ b`          | Switch to previous buffer                 |
| `<leader> b i` | Consult buffer list                       |
| `<leader> b b` | Open Ibuffer                              |
| `<leader> b d` | Kill current buffer                       |
| `<leader> b k` | Kill current buffer                       |
| `<leader> b x` | Kill current buffer                       |
| `<leader> b s` | Save buffer                               |
| `<leader> b l` | Consult buffer                            |
| `<leader>SPC`  | Consult buffer                            |
| `<leader> p b` | Consult project buffer                    |
| `<leader> p p` | Switch project                            |
| `<leader> p f` | Find file in project                      |
| `<leader> p g` | Find regexp in project                    |
| `<leader> p k` | Kill project buffers                      |
| `<leader> p D` | Dired for project                         |
| `P`            | Yank from kill ring                       |
| `<leader> P`   | Yank from kill ring                       |
| `<leader> .`   | Embark act                                |
| `<leader> u`   | Undo tree visualize                       |
| `<leader> h m` | Describe current mode                     |
| `<leader> h f` | Describe function                         |
| `<leader> h v` | Describe variable                         |
| `<leader> h k` | Describe key                              |
| `] t`          | Go to next tab                            |
| `[ t`          | Go to previous tab                        |
| `<leader> m p` | Format with Prettier                      |
| `<leader> c a` | Execute code action                       |
| `<leader> r n` | Rename symbol                             |
| `gI`           | Find implementation                       |
| `<leader> l f` | Format buffer via LSP                     |
| `K`            | Show hover documentation                  |
| `gcc`          | Comment/uncomment current line            |
| `gc`           | Comment/uncomment selected region         |
| `gd`           | Goto definitions                          |
| `gr`           | Goto references                           |

...and a lot more, discoverable with which-key :)

## Contributing

This package is intentionally designed with a specific vision in mind,
reflecting my own opinions and preferences. While contributions are
welcome, please understand that this configuration is quite
opinionated.

If you have suggestions or requests, they will be considered
carefully, but I cannot make any promises regarding implementation or
acceptance. Your input is valuable, and I appreciate any help or
feedback to improve the project.

To contribute, feel free to open an issue or submit a pull
request. Let's make this configuration even better together!

## About PRs

Always welcome, not a promise to accept though (see above). Please
direct your PRs to the `development` branch of this repository.
