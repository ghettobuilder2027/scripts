# scripts pour la vie quotidienne

## Batch convert video to mp3 

for i in *.mp4; do ffmpeg -i "$i" -b:a 32K -vn "${i%.*}.mp3"; done

## timelapse non sound
ffmpeg -i input.mp4 -filter:v "setpts=0.5*PTS" -an output.mp4


## timelapse from images
ffmpeg -framerate 30 -pattern_type glob -i "folder-with-photos/*.JPG" -s:v 1440x1080 -c:v libx264 -crf 17 -pix_fmt yuv420p my-timelapse.mp4

## rotate 
ffmpeg -i in.mov -vf "transpose=1" out.mov

## Cut videos
ffmpeg -ss 00:01:00 -i video.mp4 -to 00:02:00 -c copy cut.mp4

-to : until 

or

ffmpeg -ss 60 -i video.mp4 -t 60 -c copy cut.mp4 

t : time

## concatenate
for f in $(ls bat_*); do echo file \'$f\' >> files.txt;done

ffmpeg -f concat -safe 0 -i files.txt -c copy mergedVideo.mp4

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
  
  
  ## ssh
  https://linuxhint.com/ssh-using-private-key-linux/
  
  https://pimylifeup.com/raspberry-pi-ssh-keys/
  
  
  ## kill linux process by name
   k=$(pidof vlc); kill -9 $k

