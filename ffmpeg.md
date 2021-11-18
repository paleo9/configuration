# ffmpeg

ffmpeg is a very fast video and audio converter that can also grab from a live audio/video source.

ffmpeg can handle multiple inputs. Take care over the order of arguments for inputs and those for outputs.

## Examples

### Video and audio grabbing

```
  ffmpeg -f oss -i /dev/dsp -f video4linux2 -i /dev/video0 /tmp/out.mpg
```

```
  ffmpeg -f alsa -ac 1 -i hw:1 -f video4linux2 -i /dev/video0 /tmp/out.mpg
```

### X11 grabbing

```
  ffmpeg -f x11grab -video_size cif -framerate 25 -i :0.0 /tmp/out.mpg
```

```
  ffmpeg -f x11grab -video_size cif -framerate 25 -i :0.0+10,20 /tmp/out.mpg
```

0.0 is the display.creen number of your x11 server, same as the DISPLAY environment variable.

### Video and audio file format conversion


