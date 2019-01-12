# Youtube-MP3 Converter

Convert YouTube videos to MP3

# Requirements

1. Download `ytube` file to your preferred location where you want MP3s downloaded
1. Install python if you don't have it already `sudo apt-get install python`
1. Install `ffmpeg` `sudo apt-get install ffmpeg`
1. Install `youtube-dl` `sudo -H pip install --upgrade youtube-dl`. See https://github.com/rg3/youtube-dl

# Usage

1. Make `ytube` executable `chmod +x ytube`
1. To convert individual videos, use `./ytube -v video_id,video_id` (only use slugs not the whole URL. If URL is https://youtube.com/watch/v?=wxyz, you would copy `wxyz` e.g. `./ytube -v wxyz,abcde`
1. To convert playlists use `./ytube -p playlist_id` e.g. `./ytube -p PLgZEkAm-otxstxvlLzYxUmOStjt_C33DU`

# Potential additions

* [ ] Skip duplicates
* [ ] Error recovery
* [ ] Clean file naming

# Other methods of downloading MP3 using youtube-dl only

## Downloading single file
```bash
youtube-dl -i --extract-audio --audio-format mp3 --audio-quality 0 YOUTUBE_VIDEO_LINK
```

## Downling playlist
`-i` - ignore errors

`-c` - continue

`--extract-audio` - extract audio track

`--audio-format mp3` - convert to mp3

`--audio-quality 0` - the best audio quality

`--yes-playlist` - affirm that url points to a playlist

```bash
# Basic download
youtube-dl -ic -o "%(title)s.%(ext)s" --yes-playlist --extract-audio --audio-format mp3 --audio-quality 0 YOUTUBE_PLAYLIST_LINK

# Log successful downloads to text file
youtube-dl --download-archive downloads.txt --no-overwrites -ic  -o "%(title)s-%(id)s.%(ext)s" --yes-playlist --extract-audio --audio-format mp3 --audio-quality 0 --socket-timeout 5 YOUTUBE_PLAYLIST_LINK

# -i option to ignore errors keep trying until success
while ! youtube-dl --download-archive downloaded.txt --no-overwrites -c -o "%(title)s-%(ext)s" --yes-playlist --extract-audio --audio-format mp3 --audio-quality 0 --socket-timeout 5 YOUTUBE_PLAYLIST_LINK; do echo DISCONNECTED; sleep 5; done
```

### Disclaimer
This is tool is for educational use only. YouTube videos are copyrights of their owners and/or Youtube.com. This tool might be restricted to use in some countries.
