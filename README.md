1) Connect to ssh
2) sudo apt update && sudo apt upgrade
3) reboot
4) sudo raspi-config
5) go to 7 Advanced Options
6) go to A3 Memory split 
7) set 512mb
8) Finish and reboot
9) sudo nano /boot/cmdline.txt
10) Add consoleblank=0 
11) sudo nano /etc/rc.local
12) Delete all and paste this code (enter your rstp stream before insertion)


```
# THIS IS 9 STREAMS
#!/bin/sh -e

sleep 1s &&
#!/bin/bash
screen -dmS stream1 sh -c 'omxplayer --video_queue 1000 --refresh --live --win "0 0 640 360" rtsp://; exec bash'
screen -dmS stream2 sh -c 'omxplayer --video_queue 1100 --refresh --live --win "640 0 1280 360" rtsp://; exec bash'
screen -dmS stream3 sh -c 'omxplayer --video_queue 1200 --refresh --live --win "1280 0 1920 360" rtsp://; exec bash'

sleep 3s &&
#!/bin/bash
screen -dmS stream4 sh -c 'omxplayer --video_queue 1300 --refresh --live --win "0 360 640 720" rtsp://; exec bash'
screen -dmS stream5 sh -c 'omxplayer --video_queue 1400 --refresh --live --win "640 360 1280 720" rtsp://; exec bash'
screen -dmS stream6 sh -c 'omxplayer --video_queue 1500 --refresh --live --win "1280 360 1920 720" rtsp://; exec bash'

sleep 5s &&
#!/bin/bash
screen -dmS stream7 sh -c 'omxplayer --video_queue 1600 --refresh --live --win "0 720 640 1080" rtsp://; exec bash'
screen -dmS stream8 sh -c 'omxplayer --video_queue 1700 --refresh --live --win "640 720 1280 1080" rtsp://; exec bash'
screen -dmS stream9 sh -c 'omxplayer --video_queue 1800 --refresh --live --win "1280 720 1920 1080" rtsp://; exec bash'


exit 0
```

or

```
# THIS IS 6 STREAMS
#!/bin/sh -e

sleep 1s &&
#!/bin/bash
screen -dmS stream1 sh -c 'omxplayer --video_queue 1000 --refresh --live --win "0 0 426 360" rtsp://; exec bash'
screen -dmS stream2 sh -c 'omxplayer --video_queue 1100 --refresh --live --win "426 0 852 360" rtsp://; exec bash'
screen -dmS stream3 sh -c 'omxplayer --video_queue 1200 --refresh --live --win "852 0 1280 360" rtsp://; exec bash'

sleep 3s &&
#!/bin/bash
screen -dmS stream4 sh -c 'omxplayer --video_queue 1300 --refresh --live --win "0 360 426 720" rtsp://; exec bash'
screen -dmS stream5 sh -c 'omxplayer --video_queue 1400 --refresh --live --win "426 360 852 720" rtsp://; exec bash'
screen -dmS stream6 sh -c 'omxplayer --video_queue 1500 --refresh --live --win "852 360 1280 720" rtsp://; exec bash'
exit 0
```

13) reboot
