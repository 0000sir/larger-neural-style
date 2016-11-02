# larger-neural-style
Large size image generation with neural-style. The idea for the script comes from a combination of techniques discovered by [SwoosHkiD/bododge](https://github.com/bododge) and [ProGamerGov](https://github.com/ProGamerGov) which was post on the [Neural-Style Wiki](https://github.com/jcjohnson/neural-style/wiki/Techniques-For-Increasing-Image-Quality-Without-Buying-a-Better-GPU).


# Requirement
You should have [Neural-Style](https://github.com/jcjohnson/neural-style/) first!

And ImageMagick, install it with:

`sudo apt-get install imagemagick`

# Usage
Copy this script to neural-style directory, then run:

bigbrush.sh input_file style_file

# how it works
## 1. Generate The First Output Image:
It is recommended that you change the Neural-Style parameters to your linking.

## 2. Split The Initial Output Image Into Tiles:
Imagemagick is used to divide your first Neural-Style output image into a series of overlapping cropped images.

## 3. Run The Tiles Through Neural-Style To Increase Their Quality And Size:
The same Neural-Style parameters are then used to "U-Pres" the overlapping crop pieces, resulting in a higher resolution output. 

## 4. Feather The Tiles:

Feathering is used to blend the overlapping cropped tiles that have gone through Neural-Style in order to increase their resoltuion. Feathering values can be manipulated in order to find the best values for blending the tiles together. 

## 5. Merge The Feathered And Non-feathered Tiles Into Separate Outputs:

The feathered tiles are put back together into an image that is larger than your original Neural-Style output image.

## 6. Layer The Feathered Image Above the Non-feathered Image:

This is done to disguise the feathering that is done to blend the tiles together.
