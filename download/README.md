<a href="https://colab.research.google.com/github/rin2401/youtube/blob/master/download/Download_Youtube.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>

```python
import os
# https://github.com/yt-dlp/yt-dlp
!python3 -m pip install -U --pre "yt-dlp[default]"
!apt install ffmpeg

video_url = "https://www.youtube.com/watch?v=-_E4dZoVBXM" #@param {type:"string"}
output_dir = "/content/" #@param {type:"string"}

os.chdir(output_dir)
!pwd
!yt-dlp "{video_url}"
print("DONE")
```