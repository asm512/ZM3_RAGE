---
layout: post
title: Modelbin format introduction
permalink: /docs/_posts/
---
# The .modelbin format 
### Forza Motorsport 6 Apex, Forza Horizon 3 and Forza Motorsport 7

The .`modelbin` format is Microsoft's proprietary file format used to store 3D geometry about vehicles in  their most recent game instalments. The `.modelbin` texture equivalent is `.swatchbin`, which you can read about more [here](https://forum.xentax.com/viewtopic.php?f=16&t=4256). Said thread also contains information on information  regarding the `.modelbin` format.


# Extraction

If you've got the game, dumping it to gain access to otherwise encrypted files, will require your game to be reinstalled, however if you want to do this use Wunkolo's [UWP Dumper](https://github.com/Wunkolo/UWPDumper). Otherwise, you can find the unencrypted archives on either [3D models ](https://www.facebook.com/3Dcarmodels/) or [Gamemodels](http://gamemodels.ru).

Depending on which game you took your vehicle from, the parent directories must be set accordingly, respecting the original game structure. In the archive, unpack the folder into the following directories. Make sure the folder name is the same as the `.carbin` name inside of  the archive
>Forza Motorsport 6

	Apex/media/game/cars/
	
>Forza Horizon 3

	FH3\media\cars
	
>Forza Motorsport 7

	FM7/media/cars
	

## Conversion

After you have the folder tree setup properly, it's time to import the archive into 3dSimED. Depending on which game your vehicle is from, you'll need to specify an import filter. These can be specified in the `import` window, where the names are self-explanatory. Once you've selected the correct import filter, navigate to the vehicle folder, and select the main `.carbin` file inside. This should import the whole vehicle into 3dSimED. If you experience any crashes during attempting to load the model, this usually means your folder tree is incorrect, you can check the correct folder tree by opening any `.modelbin` in Notepad++, and looking at any material references. These will for example look like `Game:\Media\cars\_library\materials\specificuse\backfacinggeo.materialbin`. From this we can see that the correct folder tree would be `GAMENAME/media/cars/YOUR_FOLDER_GOES_HERE`.


## Exporting to a native format

Sadly 3dSimED doesn't support `.fbx`, but then neither does ZM. Here, the export options change depending on where you want to prepare your model. As a personal preference I would use 3DS Max to prepare the model (UV mapping, material sorting, part renaming). However for the sake of this tutorial I'm going to describe how to import it straight into ZM. Once you've imported the entire model into 3dSimED, head over to the export tab and select rFactor2. On the dropdown menu select export objects, and select the target destination folder to which to export the objects to. Each `.modelbin` inside the vehicle folder is exported as a separate `.gmt`, which is a format that ZM can import. Once it's exported these, you can optionally export the textures too, however I'd reccomend using a different tool to export textures.

## Importing to Zmodeler3

`.gmt`  files require no further editing and can be imported into ZM easily. Strictly due to the fact that these new models have up to 200 materials each, which provide an opportunity for making the vehicle look as accurate as possible, I'd recommend importing one part at a time and devoting as much time as is needed to said part. When working on materials, I would recommend not to change the name of the materials if possible, since when importing another `.gmt` which uses the same material, it won't merge with the renamed one, but will instead create a new one, which otherwise would not be a problem, however GTA V has a limit to the amount of materials that  a single vehicle can have, which if surpassed will result in an unspawnable vehicle. The only materials which I would suggest doing from scratch would be light and glass materials in  certain cases.

## Materials

Unlike the old tool for `.modelbin` formats, 3dSimED manages to sustain materials and UV maps too (most of them will need to be remapped anyway). Due to the high amount of materials, it is best practice to learn how to optimise materials as much as possible. This includes merging similar materials, such as plastic or metals. It is also important to learn to use the appropriate shaders, as these influence the look of the vehicle greatly. 

When importing lights into your scene, I'd recommend making emissive materials from scratch, as the exported ones can be very confusing, and aren't needed for GTA since they are optimized to use new DX12 features. 1 emissive material for all lights is enough for GTA V.


|                |Short desc.                          |                        
|----------------|-------------------------------|
|**Vehicle_mesh**|Used in metallic materials e.g. brushed metal, chrome, mirrors|
