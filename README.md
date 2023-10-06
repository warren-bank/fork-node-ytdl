# node-ytdl

A youtube downloader written in Javascript. To be used with the command line. If you're looking to use it in your node program, check out [ytdl-core](https://github.com/warren-bank/fork-node-ytdl-core).


# Usage

Streams to stdout by default

    ytdl "http://www.youtube.com/watch?v=_HSylqgVYQI" | mpv -

To save to a file

    ytdl "http://www.youtube.com/watch?v=_HSylqgVYQI" > myvideo.mp4

or

    ytdl -o "{author.name} - {title}" "http://www.youtube.com/watch?v=_HSylqgVYQI"


Download video and convert to mp3 (Requires ffmpeg)

```bash
ytdl http://www.youtube.com/watch?v=_HSylqgVYQI | ffmpeg -i pipe:0 -b:a 192K -vn myfile.mp3
```


Supported options

    Usage: ytdl <url> [options]

    url
      URL to the video.

    Options:
      -V, --version                   output the version number
      -q, --quality <ITAG>            Video quality to download, default: highest
      -r, --range <INT>-<INT>         Byte range to download, ie 10355705-12452856
      -t, --timerange <TIME>-<TIME>   Time range to download, ie 1m30s-2m30s
      -b, --begin <TIME>              Time to begin video, format by 1:30.123 and
                                      1m30s
      -o, --output <FILE>             Save to file, template by {prop}, default:
                                      stdout or {title}
      --filter <STR>                  Can be video, videoonly, audio, audioonly,
                                      audioandvideo, videoandaudio
      --filter-container <REGEXP>     Filter in format container
      --unfilter-container <REGEXP>   Filter out format container
      --filter-resolution <REGEXP>    Filter in format resolution
      --unfilter-resolution <REGEXP>  Filter out format resolution
      --filter-codecs <REGEXP>        Filter in format codecs
      --unfilter-codecs <REGEXP>      Filter out format codecs
      -i, --info                      Print video info without downloading
      -j, --info-json                 Print video info as JSON without downloading
      --print-url                     Print direct download URL
      --no-cache                      Skip file cache for html5player
      -h, --help                      display help for command


# Install

    npm -g install @warren-bank/ytdl


# Tests
Tests are written with [mocha](https://mochajs.org)

```bash
npm test
```
