# coc-markmap

Visualize your Markdown as mindmaps with [markmap-lib](https://github.com/gera2ld/markmap/tree/master/packages/markmap-lib).

This is an extension for [coc.nvim](https://github.com/neoclide/coc.nvim).

If you prefer a CLI version, see [markmap-cli](https://github.com/gera2ld/markmap/tree/master/packages/markmap-cli).

Note: *coc-markmap* allows generating markmaps from current buffer or selected text, while the CLI version can only create markmaps from Markdown files.

<img src="https://user-images.githubusercontent.com/3139113/72221499-52476a80-3596-11ea-8d15-c57fdfe04ce0.png" alt="markdown" width="300"> <img src="https://user-images.githubusercontent.com/3139113/72221508-7014cf80-3596-11ea-9b59-b8a97bba8e1c.png" alt="mindmap" width="300">

## Installation

First, make sure [coc.nvim](https://github.com/neoclide/coc.nvim) is started.

Then install with the Vim command:

```
:CocInstall coc-markmap
```

## Usage

### Generating markmap HTML

Open a Markdown, and execute:

```viml
:CocCommand markmap.create
```

An HTML file with the same basename as the Markdown file will be created and opened in your default browser. If there is a selection, it will be used instead of the file content.

Transforming plugins are enabled by default, including syntax highlight with [PrismJS](https://prismjs.com/) and math typesetting with [Katex](https://katex.org/).

### Watching mode

There is also a watching mode:

```viml
:CocCommand markmap.create -w
```

The node under cursor will always be visible in the viewport on cursor move.

## Configurations

### CocConfig

You can change some global configurations for this extension in `coc-settings.json`.

First open the settings file with `:CocConfig`.

### Key mappings

There is no default key mapping, but you can easily add your own:

```viml
" Create markmap from the whole file
nmap <Leader>m <Plug>(coc-markmap-create)
" Create markmap from the selected lines
vmap <Leader>m <Plug>(coc-markmap-create-v)
```

### Commands

It is also possible to add a command to create markmaps.

```viml
command! -range=% Markmap CocCommand markmap.create <line1> <line2>
```

Now you have the `:Markmap` command to create a Markmap, either from the whole file or selected lines.
