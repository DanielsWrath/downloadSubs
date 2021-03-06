# DownloadSubs
Python script to download subtitles for movies and series

## Requirements
Please install both [subliminal](https://github.com/Diaoul/subliminal) and [mediainfo](https://mediaarea.net/nl/MediaInfo) in order for this script to function.

## Usage
Usage is as follows:
`python3 downloadSubs.py [commands] "/dir/to/videos" ["more/dirs"]`

The extra parameters are:
- `-R` to recursively search in given directories for video files
- `-l lang1,lang2,lang3,...` to override default languages. Languages have to be the default language codes (e.g. nl for Dutch) and they have to be separated by a comma, without spaces.
- `-print` to see the progress of the subtitle downloading
- `-new` to only download subtitles for files which don't already have subtitles in the given languages. (The subs do have to be of the format `[VideoName].[language].srt`, so for example: `Zootopia.en.srt`)
- `-limit -300mb+1tb` to set lower and higher limits. The `-` is for the lower limit, so it won't do anything for files smaller than 300mb and it won't do anything for files bigger than 1tb. The sized supported are `b, kb, mb, gb, tb`. Only one limit can also be set. Values have to be integer numbers

So `python3 downloadSubs.py -R -l nl,en,fr -limit -1gb "~"` will download French, Dutch and English subtitles for all video files, bigger than 1gb, in the home map and all the maps in the home dir.
