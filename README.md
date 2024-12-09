# Satellite-Line-Repair

This is a Pixinsight script for repairing satellite lines through light frames.

This will work only on mono images at present. RGB will be added as an update in the future.

The script will display any available image window in its image window frame.
The user can set the range threshold slider (default 25) and the detection threshold slider (default 50) and then selecte the detect button at the bottom of the panel.
It may take a while depending on the computer hardware and the size of the image, but satellite lines will be detected and displayed in red or green in the
script image window.

The range threshold sets the threshold of the mask range. Lower numbers means more lines detected, but more noise in the initial estimate and therefore more time to compute, and a greater chance of detecting non-satellite lines.

The detector threshold sets the threshold of the Hough Line Peak algorithm. Lower numbers means more lines detected, nbut a greater chance of detecting non-satellite lines. Set to lower if there are multiple lines of varying intensities, otherwise 50 should work.



If the selection is imperfect, either Ctrl+left mouse button will modify the selection, or start over by shift+left mouse button as above.

Once the selection is made, the execute button will modify both the image window selected in the main Pixinsight window as well as that image displayed in the image preview
in the script. The Undo button undoes the changes in both the preview window and the image window open in the main Pixinsight window.

This script works on both RGB and mono images.

The Residual star slider is the size of the star that remains after the halo has been repaired. If it is set to 0, no residual star is created.

## Uses

The script works on the star halo problem below. It also seems to work on repairing orphaned dust donuts from Ritchey-Chretien flats and images.

## Images

This is a sample pair of images. Thank you to Geoff on the Pixinsight forums for permitting me to use his image as a sample.

<img src="./figs/HalosRepaired.png" text='Repaired halos - left original, right repaired' align=left />

## Script

This is the script interface.

<img src="./figs/HaloRepairScript.png" text='Halo repair script' align=left />

## Manage repository location

In order to automatically install and subsequently refresh script updates in Pixinsight, add the following URL to Resources > Updates > Manage repositories

https://raw.githubusercontent.com/chickadeebird/Star-Halo-Pixinsight-updates/main/

After this has been added to the repositories, Check for updates should place the new JAHRsHaloRepair script in Scripts > ChickadeeScripts
