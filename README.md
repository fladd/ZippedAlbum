# ZippedAlbum
A suggestion for a self-contained music album format

## Specification
A simple ZIP file (not necessarily compressed, not necessarily with .zip ending), with the audio files in lossy (opus) or lossles (flac) format, and an optional digital booklet in PDF format (square paper size) of which the first page is the album cover. For compatility with current players, additional cover image(s) can be included.

```
├── *.[zip|zlbm|*]
│   ├── [*.[opus|flac]]+
│   ├── (*.pdf)
│   ├── ([*.[jpg|png]]+)
```

## Examples
The following ZIP files would each be recognized as a ZippedAlbum. The first example is the simplest form with all necessary information. To my knowledge this is not supported by any player yet. The last example is the format of an album download from Bandcamp. Such a ZIP file is already supported in players today (e.g. Foobar2000, DeaDBeeF). 

```
├── Artist-Album_Title.zip
│   ├── Artist-Album_Title-01-First_Song.opus
│   ├── Artist-Album_Title-02-Second_Song.opus
│   ├── Artist-Album_Title-03-Third_Song.opus
│   ├── Artist-Album_Title-04-Fourth_Song.opus
│   ├── Artist-Album_Title.pdf
```

```
├── Artist-Album_Title.zip
│   ├── Artist-Album_Title-01-First_Song.opus
│   ├── Artist-Album_Title-02-Second_Song.opus
│   ├── Artist-Album_Title-03-Third_Song.opus
│   ├── Artist-Album_Title-04-Fourth_Song.opus
│   ├── Artist-Album_Title_booklet.pdf
│   ├── back.jpg
│   ├── front.jpg
```

```
├── Artist-Album_Title.zlbm
│   ├── 01.opus
│   ├── 02.opus
│   ├── 03.opus
│   ├── 04.opus
│   ├── booklet.pdf
│   ├── folder.jpg
```

```
├── Artist - Album Title.zip
│   ├── Artist - Album Title - 01 First Song.flac
│   ├── Artist - Album Title - 02 Second Song.flac
│   ├── Artist - Album Title - 03 Third Song.flac
│   ├── Artist - Album Title - 04 Fourth Song.flac
│   ├── cover.png
```
