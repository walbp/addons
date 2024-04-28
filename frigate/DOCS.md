# Frigate-rknpu版

## 使用方法：

需要在 /mnt/data/supervisor/homeassistant/ 下面添加配置文件frigate.yaml

可以：
- 方法一：进入 [ip]:7681 导航到指定位置，使用命令行工具添加编辑frigate.yaml
- 方法二：使用 File editor 或者 Filebrowser(推荐) 添加编辑frigate.yaml

```yaml
mqtt:
  enabled: false

detectors:
  rknn_k:
    type: rknn
  #cpu2:
  #  type: cpu
  #  num_threads: 3
  #ov:
  #  type: openvino
  #  device: AUTO
  #  model:
  #    path: /openvino-model/ssdlite_mobilenet_v2.xml
model:
  width: 320
  height: 320
  input_tensor: nhwc
  input_pixel_format: bgr
  #path: default-yolov8n
  #labelmap_path: /openvino-model/coco_91cl_bkgr.txt

ffmpeg:
  input_args: preset-rtsp-restream
  hwaccel_args: preset-rk-h264
  output_args:
        record: preset-record-generic-audio-aac

#go2rtc:
#  streams:
#    frontdoor:
#      - ffmpeg:rtsp://your-rtsp/Streaming/Channels/101

#注意：下面的path后是要改成自己摄像头rtsp链接的。

cameras:
  wga-door:
    ffmpeg:
      inputs:
        - path: rtsp://your-rtsp/Streaming/Channels/101
          roles:
            - detect
detect:
  width: 1280
  height: 720
  fps: 6
  enabled: True

objects:
  track:
    - person
  filters:
    person:
      min_score: 0.2

snapshots:
  enabled: true
  bounding_box: true
  clean_copy: true
  retain:
    default: 15

record:
  enabled: true
  expire_interval: 60
  retain:
    days: 0
    mode: active_objects
  events:
    pre_capture: 3
    post_capture: 3
    objects:
      - person
    retain:
      mode: active_objects
      objects:
        person: 15
      default: 2

#这里是日志输出设置，请根据情况自行设置

logger:
  default: debug
  logs:
    ffmpeg.wga-door.detect: debug
    detect: debug
```

更多配置参考：https://docs.frigate.video/configuration/

