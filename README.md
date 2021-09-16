# scripts pour la vie quotidiene

## Batch convert video to mp3 

for i in *.mp4; do ffmpeg -i "$i" -b:a 32K -vn "${i%.*}.mp3"; done

## timelapse non sound


ffmpeg -i input.mp4 -filter:v "setpts=0.5*PTS" -an output.mp4

## youtubedl extract mp3

youtube-dl --extract-audio --audio-format mp3 <video URL>
