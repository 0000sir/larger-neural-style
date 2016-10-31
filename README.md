# larger-neural-style
Large size image generation with neural-style. The idea for the script comes from a combination of techniques discovered by [SwoosHkiD](https://www.reddit.com/user/SwoosHkiD) and [ProGamerGov](https://github.com/ProGamerGov) which was post on the [Neural-Style Wiki](https://github.com/jcjohnson/neural-style/wiki/Techniques-For-Increasing-Image-Quality-Without-Buying-a-Better-GPU).


# Requirement
You should have [Neural-Style](https://github.com/jcjohnson/neural-style/) first!

And ImageMagick, install it with:

`sudo apt-get install imagemagick`

# Usage
Copy this script to neural-style directory, then run:

bigbrush.sh input_file style_file

Make sure you have an 'output' directory of generated files

# how it works
## 1. Generate a small size image
1000px in this script, I use GTX1080 to do it. The Neural-Style parameters in the script are easy to change to your linking.

## 2. Split it to 3x3 tiles
Imagemagick is used to divide your first Neural-Style output image into a series of overlapping cropped images.

## 3. Neural style transfer
The same Neural-Style parameters are then used to "U-Pres" the overlapping crop pieces, resulting in a higher resolution output. 

## 4. Feather tiles

Feathering is used to blend the overlapping cropped tiles that have gone through Neural-Style in order to increase their resoltuion. Feathering values can be manipulated in order to find the best values for blending the tiles together. 

## 5. Merge tiles

The feathered tiles are put back together into an image that is larger than your original Neural-Style output image.

