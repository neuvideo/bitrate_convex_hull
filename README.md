# Bitrate convex hulls for YT UGC videos

## Overview
This is a dataset of the bitrate convex hulls for videos in the [YT UGC dataset](https://media.withyoutube.com/). 
A bitrate convex hull, defined [here](https://netflixtechblog.com/per-title-encode-optimization-7e99442b62a2), is the set of 
bitrate-resolution mappings across all bitrates for a video, where the resolution at each bitrate is chosen such that
the video has the highest quality (in terms of [VMAF](https://github.com/netflix/vmaf)) when it is encoded to that resolution. 

The H264 CRF 10 versions of the YT UGC videos are used, with videos of height greater than 1080 excluded. Each video is
encoded to at most 5 different resolutions and at most 20 different bitrates between the original video bitrate and 150kbps. 

The encoding resolutions are
```
1080x1920
720x1280
540x960 
360x640
270x480
```


The convex hull for each video is stored in a JSON file in the following 
format.
```
[
   {
       "Resolution": {
            "Height": height,
            "Width":  width
        },
       "Rate": "bitrate",
       "VmafScore": "score"
   },
        ...
]
```

## License

[MIT](https://choosealicense.com/licenses/mit/)

