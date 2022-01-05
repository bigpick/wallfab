# :sparkles: Wallfab :sparkles:

> Programmatically generate minimally beautiful backgrounds
> with a color palette of your choice.

... (yet **_another_**) Highly configurable, programmatic wallpaper generator.

## Requirements

* [Python 3.10.x](https://www.python.org/downloads/)
* [pipenv](https://pipenv.pypa.io/en/latest/)

## Palettes/Themes

Wallfab ships with an extensive default set of [palettes](./palettes), including:

* [Dracula](https://draculatheme.com/)
* [Tokyonight -- and it's flavors](https://github.com/folke/tokyonight.nvim)
* [Nord](https://www.nordtheme.com/)
* [Gruvbox](https://github.com/morhetz/gruvbox)
* [Gotham](https://github.com/whatyouhide/vim-gotham)
* [Spaceduck](https://github.com/pineapplegiant/spaceduck)
* [Perfect Cell -- the best DBZ villian;)](https://wallpaperaccess.com/full/6357054.jpg)

... yet is able to handle many more, and adding more themes is easy as :cake: -- Simply
create a new `.json` file in the `./palettes/` directory, then either
update your config file with the new theme name, or specify `-p <NAME>`
as a command line option (and when you're done be sure to throw a PR out
so the community can leverage it too!)

## Running

The default [config.toml](./config.toml) is set to a sane prefault, so
simply running the script with no `-h` should give a good example of what
the tool does (it is set to Dracula by default).

```bash
pipenv run -- ./wallfab.py
```

To customize the run to your liking, you can either modify the config file,
or override individual options using the command line flags. Note, the
command line arguments take precedence over the config file's values.

```text
pipenv run -- ./wallfab.py -h
usage: wallfab.py [-h] [-c FILE] [-r {standard,high,full_hd,quad_hd,two_k,four_k,eight_k}] [-p PALETTE] [-b BACKGROUND] [-a ACCENTS] [-s ACCENT_SCALING] [-t {fill,outline}] [--accent-outline ACCENT_OUTLINE]

options:
  -h, --help            show this help message and exit
  -c FILE, --config_file FILE
                        Specify path to config file
  -r {standard,high,full_hd,quad_hd,two_k,four_k,eight_k}, --resolution {standard,high,full_hd,quad_hd,two_k,four_k,eight_k}
                        Specify resolution of generated wallpaper.
  -p PALETTE, --palette PALETTE
                        Name of color palette to use. I.e, name of JSON file in palettes/ dir.
  -b BACKGROUND, --background BACKGROUND
                        Name of color from palette to use as the background color.
  -a ACCENTS, --accents ACCENTS
                        Name of colors from palette to use for accents (i.e non background); can be CSV names from the palette (e.g 'red,cyan'), or one of two special values: 'all' will use all colors, and 'almost-all' will use all but the
                        current background color.
  -s ACCENT_SCALING, --accent-scaling ACCENT_SCALING
                        The scaling of the accents; ie. determines how big or small they are. Provided value is used to divide the desired resolution's width/height to determine size (so smaller values results in larger accents, and larger
                        values results in smaller/more accents.
  -t {fill,outline}, --accent-type {fill,outline}
                        Type of accent to be rendered; default is filled
  --accent-outline ACCENT_OUTLINE
                        Width/thickness of accent outline; ONLY relevant if accent_type is set to 'outline' -- unused when set to 'fill'
```
