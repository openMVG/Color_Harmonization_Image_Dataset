Image dataset used for Color Harmonization experiments [1].

[1] Global Multiple-View Color Consistency.
Moulon Pierre, Duisit Bruno and Monasse Pascal. CVMP 2013.

Photographer: Copyright 2013 Pierre MOULON

Run:

```
#Init the scene
$ openMVG_main_SfMInit_ImageListing -i $path/Color_Harmonization_Image_Dataset/Scene1/images/ -o $path/Color_Harmonization_Image_Dataset/Scene1/matches

#Compute features for each used images
$ openMVG_main_ComputeFeatures -i $path/Color_Harmonization_Image_Dataset/Scene1/matches/sfm_data.json -o $path/Color_Harmonization_Image_Dataset/Scene1/matches/

#Compute Regions matches & geometric coherent matches (here Homography matches are used, since the scene is flat)
$openMVG_main_ComputeMatches -i $path/Color_Harmonization_Image_Dataset/Scene1/matches/sfm_data.json -o $path/Color_Harmonization_Image_Dataset/Scene1/matches/ -g h

#Compute the color harmonization (use image id 1 as reference, and geometric coherent feature point color for harmonization)
$ openMVG_main_ColHarmonize -i $path/Color_Harmonization_Image_Dataset/Scene1/matches/sfm_data.json -m $path/Color_Harmonization_Image_Dataset/Scene1/matches/matches.h.bin -o $path/Color_Harmonization_Image_Dataset/Scene1/matches/ -s 1 -r 1

```

