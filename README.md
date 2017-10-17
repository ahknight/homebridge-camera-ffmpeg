# homebridge-camera-ffmpeg-amcrest

Amcrest camera plugin for [Homebridge](https://github.com/nfarina/homebridge)

## Installation

1. Install ffmpeg
2. Install this plugin using: npm install -g ahknight/homebridge-camera-ffmpeg-amcrest
3. Edit ``config.json`` and add the camera.
3. Run Homebridge
4. Add extra camera accessories in Home app. The setup code is the same as homebridge.

### Config.json Example

    {
      "platform": "Camera-ffmpeg-amcrest",
      "cameras": [
        {
          "name": "Camera Name",
          "videoConfig": {
          	"source": "-re -i rtsp://myfancy_rtsp_stream",
            "stillImageSource": "-i http://faster_still_image_grab_url/this_is_optional.jpg",
          	"maxStreams": 2,
          	"maxWidth": 1280,
          	"maxHeight": 720,
          	"maxFPS": 30
          }
        }
      ]
    }

* Optional parameter vcodec, if you are running on a RPi with the omx version of ffmpeg installed, you can change to the hardware accelerated video codec with this option.

```
{
  "platform": "Camera-ffmpeg-amcrest",
  "cameras": [
    {
      "name": "Camera Name",
      "videoConfig": {
      	"source": "-re -i rtsp://myfancy_rtsp_stream",
        "stillImageSource": "-i http://faster_still_image_grab_url/this_is_optional.jpg",
      	"maxStreams": 2,
      	"maxWidth": 1280,
      	"maxHeight": 720,
      	"maxFPS": 30,
      	"vcodec": "h264_omx"            
      }
    }
  ]
}
```
