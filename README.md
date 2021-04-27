# ZippedAlbum
A suggestion for a self-contained music album format

## Specification
A simple ZIP file (not necessarily compressed, not necessarily with .zip extension), with properly tagged (title, albumartist/artist, tracknumber, date) audio files in lossy (Opus) or lossles (FLAC) format, and an optional digital booklet in PDF format (square paper size) of which the first page is the album cover. For compatility with current players, additional (cover) image(s) can be included. For quickly creating custom compilations/mixtapes without changing the tags of the included audio files, an optional playlist (XSPF) might specify the title, creator and order of tracks.

```
├── *.zip|zlbm|*
│   ├── *.opus|flac
│   ├── *.opus|flac
│   ├── ...
│   ├── (*.pdf)
│   ├── (*.jpeg|png)
│   ├── (*.jpeg|png)
│   ├── ...
|   ├── (*.xspf)
```

## Examples
The following ZIP files would each be recognized as a ZippedAlbum. While I am not aware of any player that suports showing the PDF booklet (I am working on one though!), there are players that will play the audio and show the cover image if present (e.g. Foobar2000, DeadBeeF).

**Simplest form with a PDF booklet:**
```
├── Artist-Album_Title.zip
│   ├── Artist-Album_Title-01-First_Song.opus
│   ├── Artist-Album_Title-02-Second_Song.opus
│   ├── Artist-Album_Title-03-Third_Song.opus
│   ├── Artist-Album_Title-04-Fourth_Song.opus
│   ├── Artist-Album_Title.pdf
```

**Two variants with additional images:**
```
├── Artist-Album_Title.zip
│   ├── Artist-Album_Title-01-First_Song.opus
│   ├── Artist-Album_Title-02-Second_Song.opus
│   ├── Artist-Album_Title-03-Third_Song.opus
│   ├── Artist-Album_Title-04-Fourth_Song.opus
│   ├── Artist-Album_Title_booklet.pdf
│   ├── back.jpeg
│   ├── front.jpeg
```

```
├── Artist-Album_Title.zlbm
│   ├── 01.opus
│   ├── 02.opus
│   ├── 03.opus
│   ├── 04.opus
│   ├── booklet.pdf
│   ├── folder.jpeg
```

**The format of an album downloaded from Bandcamp, inlcuding only a cover image:**
```
├── Artist - Album Title.zip
│   ├── Artist - Album Title - 01 First Song.flac
│   ├── Artist - Album Title - 02 Second Song.flac
│   ├── Artist - Album Title - 03 Third Song.flac
│   ├── Artist - Album Title - 04 Fourth Song.flac
│   ├── cover.png
```

**A custom made mixtape that includes neither a PDF booklet nor any images, but a playlist:**
```
├── fladdsAwesomeMixtape.zip
│   ├── ArtistA_TitleW.opus
│   ├── ArtistB_TitleX.opus
│   ├── ArtistC_TitleY.opus
│   ├── ArtistD_TitleZ.opus
│   ├── playlist.xspf

```

Contents of playlist.xspf:

```
<?xml version="1.0" encoding="UTF-8"?>
<playlist version="1" xmlns="http://xspf.org/ns/0/">

    <title>Awesome Mixtape</title>

    <creator>fladd</creator>

    <trackList>
        <track>
            <location>ArtistB_TitleX.opus</location>
        </track>
        <track>
            <location>ArtistD_TitleZ.opus</location>
        </track>
        <track>
            <location>ArtistC_TitleY.opus</location>
        </track>
        <track>
            <location>ArtistA_TitleW.opus</location>
        </track>
    </trackList>
</playlist>
```
