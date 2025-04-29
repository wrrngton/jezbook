# FFmpeg

FFmpeg is a CLI tool for processing and manipulating video, audio files.

I mainly use this for cutting and processing audio (usually music sets)

## Params to know

- `-ss`: start time
- `-to`: end time 
- `-i`: input audio, e.g file.m4a
- `-c copy`: copies to output without re-encoding for faster processing 

### Cut audio from timestamp to end

```console
ffmpeg -ss 2:30:00 -i set.m4a -c copy output.m4a
```
### Cut audio between two timestamps

```console
ffmpeg -ss -i set.m4a 00:13:16 -t 00:14:53 -c copy output.m4a
```




