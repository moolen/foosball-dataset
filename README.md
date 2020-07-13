# Foosball Dataset
This repository contains labeled images of various foosball tables.

Tables (so far):
* lenhart
* vector black-white

## Data Organization
This dataset is organized by manufacturer. Every manufacturer has its own set of figures and color-scheme.

The source of the data must be provided.

```
.
├── leonhart # the table manufacturer
│   └── black-green # flavor of table (e.g. color-scheme or specific model)
│       └── 01 # dataset number for this manufacturer/table combination
│           ├── pictures # contains the sourced pictures
│           └── out # contains the label information
│               └── YOLO_darknet
├── vector # table
├── vector #
...
```
## Labeling

```bash
$ make label TABLE=leonhart KIND=black-green DS=01
```

## Sourcing data

1. Fetch a video file from youtube or wherever e.g. using `youtube-dl`
2. Split the video file into frames

```sh
$ youtube-dl "https://www.youtube.com/watch?v=aAXxONJDB0A"
# ... writes a file to ./path/to/video-file

# now extract every nth frame from the video
# writing it to the pictures dir: ./leonhart/black-green/83/pictures
$ make split TABLE=leonhart KIND=black-green DS=83 INPUT=./path/to/video-file

# now, proceed with labeling
$ make label TABLE=leonhart KIND=black-green DS=83
```


## Training the Dataset
This is not yet implemented.