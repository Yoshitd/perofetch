# perofetch

A small, fast, dependency-free system fetch for your terminal — a bold **PERO**
banner in a warm sunset gradient, followed by a clean readout of your OS,
kernel, memory, packages and uptime.

It's a single POSIX `sh` script. No runtime, no config files, no installer.

```
  ██████╗ ███████╗██████╗  ██████╗
  ██╔══██╗██╔════╝██╔══██╗██╔═══██╗
  ██████╔╝█████╗  ██████╔╝██║   ██║
  ██╔═══╝ ██╔══╝  ██╔══██╗██║   ██║
  ██║     ███████╗██║  ██║╚██████╔╝
  ╚═╝     ╚══════╝╚═╝  ╚═╝ ╚═════╝

  yoshi@mahbuh
  ────────────────────────────────
    os      macOS 26.4
    kernel  25.4.0
  󰍛  memory  11841/16384 MiB (72%)
  󰏔  pkgs    65 (brew)
  󰅶  uptime  2 days, 7 hours, 23 mins
    colors  ███████████████████
```

## Features

- 🌅 PERO wordmark banner in a sunset gradient (256-color).
- 🖥️ Detects OS, kernel, memory usage, package count, and uptime.
- 🍎 Works on macOS, Linux (incl. Android/Termux), and the BSDs.
- 🔤 Nerd Font icons by default, with optional Phosphor / Cozette / emoji icon sets.
- 🪶 Pure POSIX `sh`, single file, zero dependencies.

## Install

```sh
# Clone and link into your PATH
git clone https://github.com/Yoshitd/perofetch.git
install -m 0755 perofetch/bin/perofetch ~/.local/bin/perofetch
```

Make sure `~/.local/bin` is on your `PATH`:

```sh
export PATH="$HOME/.local/bin:$PATH"
```

Then just run:

```sh
perofetch
```

### Run it on every new terminal

Add this to your `~/.zshrc` (or `~/.bashrc`):

```sh
[[ $- == *i* ]] && command -v perofetch >/dev/null && perofetch
```

## Usage

```
perofetch         Show the fetch (default Nerd Font icons)
perofetch -p      Use Phosphor icons
perofetch -c      Use Cozette icons
perofetch -e      Use emoji icons
perofetch -v      Print version
perofetch -h      Show help
```

## Requirements

- A POSIX shell (`sh`).
- A terminal with 256-color support (virtually all modern terminals).
- For the default icons: a [Nerd Font](https://www.nerdfonts.com/). If you see
  boxes instead of icons, install a Nerd Font or run with `-e` for emoji.

## Customising the colors

Open `bin/perofetch` and look for the `DEFINE COLORS` and
`USER VARIABLES` sections near the bottom. Each color is a 256-color escape like
`\033[1;38;5;208m` where `208` is the color number (0–255). Change the numbers to
re-theme it in seconds.

## Credits

System-detection logic is adapted from
[nerdfetch](https://github.com/chick2d/nerdfetch) (MIT). The banner, layout and
sunset palette are original to perofetch.

## License

MIT — see [LICENSE](LICENSE).
