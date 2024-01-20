# Stephanie Wilkinson | Personal Site

```sh
# running locally
bin/bridgetown start

# build & deploy to production
bin/bridgetown deploy

# load the site up within a Ruby console (IRB)
bin/bridgetown console
```


# Optimizing images

I'm using oxipng for pngs and imageoptim for jpgs.

Usage

```sh
imageoptim *.jpg
oxipng -o 6 *.png

