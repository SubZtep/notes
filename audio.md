Web Audio

## Keywords and Buzzwords

### Audio Parameters

#### Number Of Channels

Usually it refers to output channels. Values can be 1 for Mono, 2 for Stereo, etc.

#### Sample Rate or Bits Per Second

Amount of data per second. For example an audio CD has 44100 and mp3 could be 128kbit. Low sample rate causes gaps between frames, high sample rate good for slow down sound but captures ultrasonic frequencies that interfere.

#### Sample Size or Bit Depth or Bits Per Sample

How many bits are used to record the audio. All of the electronic components of recording are generating some noise. With higher bit depth can record at lower levels and even increased volume has less noise. Audio CD uses 16 bit, but more preferable, 24 bit is pretty good.

#### Buffer Size

Amount of time allocated for processing audio. For recording and monitoring you want to hear back the result as quickly as possible so keep it low like 68 samples. For mixing plugins and effects requires computing power so better to keep it high like 1024 samples.

### JavaScript Types

#### ArrayBuffer

Fixed length memory area. To access individual bytes another view object is required.

#### DataView

View object for access and manipulate an ArrayBuffer.

## Misc

display normalise scale (-1 to 1) instead of (khz) for different bitrate audio files.

```sh
sox -t raw -r 44100 -b 32 -c 1 -L -e float xxx.raw xxx.wav
```
