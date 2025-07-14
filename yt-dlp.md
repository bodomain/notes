https://wiki.archlinux.org/title/Yt-dlp
usage:  
```
yt-dlp 'https://www.youtube.com/watch?v=nNO5Ur8mpEc'
```

`config`: 
```bash config
--ignore-errors
--no-playlist

# Save to ~/Videos
#-o ~/Videos/%(date)

-o "$HOME/Videos/$(date +%F).%(ext)s" 

# Max 360p video + medium audio (~128kbps)
-f "bestvideo[height<=360]+bestaudio[abr<=128]/best[height<=360]"
```
