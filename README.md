# Satellite-Line-Repair

This is a Pixinsight script for repairing satellite lines through light frames.

This will work only on mono images at present. RGB will be added as an update in the future.

The script will display any available image window in its image window frame.
The user can set the range threshold slider (default 25) and the detection threshold slider (default 50) and then selecte the detect button at the bottom of the panel.
It may take a while depending on the computer hardware and the size of the image, but satellite lines will be detected and displayed in red or green in the
script image window.

The range threshold sets the threshold of the mask range. Lower numbers means more lines detected, but more noise in the initial estimate and therefore more time to compute, and a greater chance of detecting non-satellite lines.

The detector threshold sets the threshold of the Hough Line Peak algorithm. Lower numbers means more lines detected, nbut a greater chance of detecting non-satellite lines. Set to lower if there are multiple lines of varying intensities, otherwise 50 should work.

Once lines are detected, they should be displayed on the view panel in red or green and can be toggled on and off with a mouse click in the script image window. If the detections are imperfect, changing the thresholding parameters and rerunning the script should display freshly detected lines, discarding the previous detected lines.

After the detected lines are satisfactory, the Repair button will apply a repair mask to the image and replace the lines with a local median value.

I should probably say that this script should not replace good acquisition practices of acquiring many images with appropriately-set Windorized sigma values, but some of us live in cloud city and only see clear skies once or twice a season (exaggerating of course).

## Uses

The script works on the satellite line problem below.

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
