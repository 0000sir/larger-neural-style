# larger-neural-style
Large size image generation with neural-style


# Requirement
You should have [Neural-Style](https://github.com/jcjohnson/neural-style/) first!

# Usage
Copy this script to neural-style directory, then run:

bigbrush.sh input_file style_file

Make sure you have an 'output' directory of generated files

# how it works
## 1. Generate a small size image
1000px in this script, I use GTX1080 to do it.

## 2. Split it to 3x3 tiles
use imagemagick to do it

## 3. Neural style transfer
Apply neural-style to each tile

## 4. Feather tiles

## 5. Merge tiles


