# scripts pour la vie quotidiene

## Batch convert video to mp3 

for i in *.mp4; do ffmpeg -i "$i" -b:a 32K -vn "${i%.*}.mp3"; done
