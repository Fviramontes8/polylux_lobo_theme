# Lobo theme for Polylux package in Typst

## Installing Polylux locally
You can use [polylux](https://github.com/andreasKroepelin/polylux) normally by importing it like this:
```typst
#import "@preview/polylux:0.3.1": *
```

But to use the lobo theme we need to use the package locally

#### Installing Polylux locally
Typst reads local packages from the `~/.local/share/typst/packages/local/`
folder and requires the folder structure for local packages to stored as
`package_name/version`, so we need to add a `polylux` folder to
`~/.local/share/typst/packages/local/` resulting in
`~/.local/share/typst/packages/local/polylux/`

Create the local folder and install polylux version 0.3.1

```sh
mkdir -p ~/.local/share/typst/packages/local/polylux/
cp ~/.local/share/typst/packages/local/polylux/
git clone https://github.com/andreasKroepolin/polylux 0.3.1 -b v0.3.1
```

You can then copy the theme to 
`~/.local/share/typst/packages/local/polylux/0.3.1/themes`

```sh
cp /path/to/theme/lobo.typ ~/.local/share/typst/packages/local/polylux/0.3.1/themes
```

Make sure to update themes.typ to include the newly added theme
```sh
cd ~/.local/share/typst/packages/local/polylux/0.3.1/themes
cat '#import "lobo.typ"' >> themes/themes.typ
```

Then you can use this to import the theme into typ files

```typst
#import "@local/polylux:0.3.1": *
#import themes.lobo: *
```
