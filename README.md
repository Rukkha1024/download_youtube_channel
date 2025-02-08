# 특정 유튜브 채널 영상 다운받기


# FFmpeg 설치 

[윈도우에서 FFmpeg 설치하는 방법](https://www.lainyzine.com/ko/article/how-to-install-ffmpeg-on-windows-10/) 

위 링크에서 FFmpeg 설치하는 법 따라하기 

# 유튜브 영상 다운 

``` python 
import yt_dlp

import os

  

# Define the channel URL and the output directory.

channel_url = 'https://www.youtube.com/@XXXXX'  # USE THE FULL URL HERE

output_directory = r'XXX'

  

# Create the output directory if it doesn't exist.

os.makedirs(output_directory, exist_ok=True)

  

# Set up the yt-dlp options.

ydl_opts = {

    'outtmpl': os.path.join(output_directory, '%(title)s [%(id)s].%(ext)s'),

    'format': 'bv*+ba/b',

    'continue': True,

    'ignoreerrors': True,

    'nooverwrites': True,

    'verbose': True,

}

  

# Create a yt-dlp object.

with yt_dlp.YoutubeDL(ydl_opts) as ydl:

    # Download the videos from the channel.

    ydl.download([channel_url])  # Use the full URL here too

  

print(f"Finished downloading videos from {channel_url} to {output_directory}")
```


- 출처: [GitHub - yt-dlp/yt-dlp: A feature-rich command-line audio/video downloader](https://github.com/yt-dlp/yt-dlp)
