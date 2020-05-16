### Flatten Dir

Copies every file in a directory recursively to a target directory.
Renames every file to start with a prefix of the directories walked to avoid naming collisions.
Directories are relative to the `cwd` or current working directory.

#### Install
```
npm i -g flatten-dir
```

#### Usage without args
```
flatten-dir
```
Will use `cwd` as the root directory and will copy every file into a new directory `flatten-dir`

#### Usage with args. Every arg is optional.
```
flatten-dir --rootdir="downloads" --outputdir="downloadsflattened"
```
The `rootdir` will be interpreted as `cwd/rootdir`. In this case `cwd/downloads`
The `outputdir` will be interpreted as `cwd/outputdir`. In this case, `cwd/downloadsflattened`


#### Example
```
if rootdir contains the following structure:

rootdir
	|=images
		|=animals
			|-dog.png
			|-wolf.png
	|=audio
		|=animals
			|-bark.mp3
			|-howl.mp3
		|=nature
			|-waterfall.mp3

The files in the outputdir will be the following:

outputdir
	|-images-animals-dog.png
	|-images-animals-wolf.png
	|-audio-animals-bark.mp3
	|-audio-animals-howl.mp3
	|-audio-nature-waterfall.mp3
```