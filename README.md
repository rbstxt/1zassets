# 1zassets

Video streams for [1zworks.com](https://1zworks.com), served with GitHub Pages at
`https://rbstxt.github.io/1zassets/`.

```
videos/<slug>/master.m3u8        HLS master playlist, highest rendition first
videos/<slug>/<height>p/          one folder per rendition
    index.m3u8                    media playlist
    init.mp4, seg_000.m4s, ...    fMP4 segments (~4 s)
```

Each work is encoded from its best available source with the `scripts/encode-hls.py`
script in the site repository: H.264 High, renditions from 144p up to the source
height (2160p at most). 720p and up keep the source frame rate; 480p and below are
capped at 30 fps.

Audio is rebuilt from the music inside each work's project file
(`scripts/project-audio.py`: placement, volume keyframes and clip speed taken from
the project), encoded once to AAC at 256 kb/s and placed so the song starts exactly
on the first frame. Waiting for you keeps the audio of its published video, because
part of its soundtrack came from video clips that are missing from its project file.

Project files, thumbnails and the site itself are served from Cloudflare, not from here.
