# Convert DAV files into MP4

This script extracts DAV files from the DVR file system (Q-See DVR with DHFS4.1 file system in my use case). The videos end up with a file name indicating the camera and date/time range of the video such as:

    Cam_6_23.08.27_00_00_18-23.08.27_00_00_26_1434808031886_1434810041320.dav

To convert the DAV files into MP4, I did this:

1. Install `ffmpeg`
2. Convert with this command:

    ffmpeg -i video.dav -c:v copy -c:a copy output_video.mp4

3. To do this on a whole directory and append *.mp4 to existing file names, I did this:

    find . -type f -name '*.dav' -exec ffmpeg -i {} -c:v copy -c:a copy {}.mp4 \;
