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
script in the site repository: H.264 High + AAC-LC 128 kb/s, renditions from 144p up
to the source height (2160p at most). 720p and up keep the source frame rate; 480p
and below are capped at 30 fps.

Project files, thumbnails and the site itself are served from Cloudflare, not from here.
