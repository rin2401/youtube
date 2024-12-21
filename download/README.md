<a href="https://colab.research.google.com/github/rin2401/youtube/blob/master/download/Download_Youtube.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

```python
# https://github.com/yt-dlp/yt-dlp
!python3 -m pip install -U --pre "yt-dlp[default]"
!apt install ffmpeg

import os
from google.colab import files
import yt_dlp

video_url = "https://www.youtube.com/watch?v=DGAxrRHrxJE" #@param {type:"string"}
output_dir = "/content/" #@param {type:"string"}

os.chdir(output_dir)

yt_opts = {
    'verbose': True,
}

ydl = yt_dlp.YoutubeDL(yt_opts)
info = ydl.extract_info(video_url)
filepath = info["requested_downloads"][0]["filepath"]
files.download(filepath)
```