## 1 Prepare & Build

```
rm -rf build
git checkout -- build
git submodule update --init --recursive
docker run --rm -it -v ./:/mnt -w /opt kagamihi/ffmpeg.js
cp -a /mnt/{.git,build,Makefile} . && source /root/emsdk/emsdk_env.sh && make && cp ffmpeg*.js /mnt
```

## 2 Remove NodeJS deps
Exit from docker

Next find in vscode regexp `require\("\w+"\)` with filter `./*.js`


## 3 Move result to dist
```
rm -rf dist && mkdir dist
cp ffmpeg-worker-webm.js dist/ffmpeg-wav-to-opus-worker.js 
cp ffmpeg-webm.js dist/ffmpeg-wav-to-opus.js 
cp ffmpeg-worker-mp4.js dist/ffmpeg-wav-to-aac-worker.js
cp ffmpeg-worker-mp4.js dist/ffmpeg-wav-to-aac.js
```