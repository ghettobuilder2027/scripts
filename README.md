# scripts pour la vie quotidienne

## Batch convert video to mp3 

for i in *.mp4; do ffmpeg -i "$i" -b:a 32K -vn "${i%.*}.mp3"; done

## timelapse non sound


ffmpeg -i input.mp4 -filter:v "setpts=0.5*PTS" -an output.mp4

## combine video and audio

ffmpeg -i INPUT_FILE.mp4 -i AUDIO.wav -c:v copy -c:a aac OUTPUT_FILE.mp4

## youtubedl extract mp3

youtube-dl --extract-audio --audio-format mp3 <video URL>
  
## Scale video
  
  ffmpeg -i input.mp4 -vf scale=$w:$h <encoding-parameters> output.mp4
  
  ## freebox
  
  //mafreebox.freebox.fr/Disque\040dur /media/freebox cifs _netdev,rw,users,credentials=/home/pitou/.smbcredentials,iocharset=utf8,uid=1000,sec=ntlmv2,file_mode=0777,dir_mode=077
7,vers=1.0 0 0

## change file extension batch
  for f in *.jpeg; do
    mv -- "$f" "${f%.jpeg}.jpg"
done

  ## batch resize
  $ for i in $( ls *.jpg); do convert -resize 50% $i re_$i; done
 ## remove part of a name of a file
   sudo apt-get install rename
  rename 's/foo/bar/' *
