# Larger-Neural-Style
Creating larger Neural-Style images through automated tiling. The idea for the script comes from a combination of techniques discovered by [SwoosHkiD/bododge](https://github.com/bododge) and [ProGamerGov](https://github.com/ProGamerGov) which was posted on the [Neural-Style Wiki](https://github.com/jcjohnson/neural-style/wiki/Techniques-For-Increasing-Image-Quality-Without-Buying-a-Better-GPU).


# Requirement
You should have [Neural-Style](https://github.com/jcjohnson/neural-style/) first!

And ImageMagick, install it with:

`sudo apt-get install imagemagick`

# Usage
Copy this script to neural-style directory, then run:

`bigbrush.sh input_file style_file`

Or if you are using the 2x2 tile version, run:

`bigbrush-2x2.sh input_file style_file`

If you face a permission error, try using chmod to fix the issue: 

`chmod u+x ./bigbrush.sh`

`chmod u+x ./bigbrush-2x2.sh`

# How It Works

## 1. Generate The First Output Image:
It is recommended that you change the Neural-Style parameters for both the original and tile commands to your linking. It is recommened that the [iteration value for the tiles is set at a lower value to ensure they remain similar](https://github.com/jcjohnson/neural-style/wiki/Techniques-For-Increasing-Image-Quality-Without-Buying-a-Better-GPU). The `-save_iter` command can be used, but it may require manual editing of file names for the tiles to work.

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
