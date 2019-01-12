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

### Disclaimer
This is tool is for educational use only. YouTube videos are copyrights of their owners and/or Youtube.com. This tool might be restricted to use in some countries.
