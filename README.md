# Viu.com 1080P Video Download Script with FFmpeg

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/a8/Viu_logo.svg/796px-Viu_logo.svg.png" />

## Viu Premium subscription is not needed

### Step 1

Make sure you that have <a href="https://www.ffmpeg.org/download.html">FFmpeg</a> installed on your computer

### Step 2

Open <a href="viu.com">viu.com</a> and click on the episode you want to download, login if needed.

### Step 3

Launch ___JavaScript Console___ by clicking __Control-Shift-J__ (Command-Option-J on mac) or __Option-Command-C__ if you are using __Safari__

### Step 4

Paste this to the __Console__: 

```javascript
fileName = `'` + document.querySelector("body > div > div.wrap.clearfix > div.video-grid-m > div > div.video-detail > h1").textContent + " " + document.querySelector("body > div > div.wrap.clearfix > div.video-grid-m > div > div.video-detail > div.video-pro.ft18.clearfix > span > h2.video-update-epi").textContent + `'`

element = document.querySelector("video#bitmovinplayer-video-viu-player > source[src]").getAttribute('src')

replaced = "ffmpeg -protocol_whitelist concat,file,http,https,tcp,tls,crypto -i " + element.replace(/Layer3/g, 'Layer4') + " -c copy " + fileName + ".mp4"

console.log("Please paste the command into terminal: \n" + replaced)
```

### Step 5

Change the __terminal directory__ to the path you wanted to download to and paste the command showed in __Console__.

Hit Enter and the Video will be downloaded in 1080p H.264 MP4 format.
