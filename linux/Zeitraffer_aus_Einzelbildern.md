# Zeitraffer aus Einzelbildern

[Zeitraffer aus Einzelbildern unter Ubuntu](http://technik.elbebilder.de/2014/07/05/zeitraffer-aus-einzelbildern-unter-ubuntu/)

## 1

- `cd ~/capture`
- check if `renamed/` is available and epmty
- `./rename.sh`


## 2

cd renamed


## 3 

`for i in `ls *.jpg`; do convert ${i} -resize "1920x1920^" -gravity center -crop 1920x1080+0+0 +repage fullhd_${i}; done && aplay /usr/share/sounds/alsa/Front_Center.wav`


## 4

`ffmpeg -f image2 -i fullhd_%04d.jpg -r 25 -vb 4096k timelapse.mpg && aplay /usr/share/sounds/alsa/Front_Center.wav`

