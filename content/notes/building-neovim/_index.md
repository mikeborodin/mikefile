+++
date = '2025-10-26T00:00:00+01:00'
draft = false
title = 'Building Neovim'
showAuthor = false
+++

![feature](feature.jpg)

One can easily build neovim from sources, for that git clone it somewhere first.

```bash
git clone git@github.com:neovim/neovim.git
```

Then run the commands


```bash
make CMAKE_EXTRA_FLAGS=$"-DCMAKE_INSTALL_PREFIX=($env.HOME)/programs/neovim/out" CMAKE_BUILD_TYPE=Release

```

If we'll try to run the build/bin/nvim binary now it will show an error because we're missing the last install step.

```bash
make install
```

Finally - adding to PATH. In my `path.nu` I specify: 

```bash
path add ($env.HOME | path join "/programs/neovim/out/bin")
```

