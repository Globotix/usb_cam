usb_cam <!-- [![Build Status](https://api.travis-ci.org/bosch-ros-pkg/usb_cam.png)](https://travis-ci.org/bosch-ros-pkg/usb_cam) -->
=======
# Introduction
ARCHIVED - This Repo is no longer used for FLEXA since the changes to use Ethernet IP Camera instead of USB Camera

#### Changes Made to this Fork
This fork implements support for a few formats not supported by the original `usb_cam`. In particular, support for `H264` with `YUV420` pixel formats and `MJPEG` with `YUVJ422` pixel formats. The motivation for modifying this fork was because the USB webcam we had simply did not work with `usb_cam`, because it did not output video in the formats supported by `usb_cam`.

If you wish to stream `H264` with `YUV420` into ROS, simply run the launchfile with `<param name="pixel_format" value="h264_yuv420p" />`.

If you wish to stream `MJPEG` with `YUVJ422` into ROS, simply run the launchfile with `<param name="pixel_format" value="mjpeg_yuvj420p" />`.

For info, since this was not modified by me here, if you wish to stream `MJPEG` with `YUVJ420` into ROS, simply run the launchfile with `<param name="pixel_format" value="mjpeg" />`, though avcodec might complain that a deprecated pixel format is used. This is because the `usb_cam` was hardcoded to use `YUV420` when video feed is `MJPEG`, but `YUVJ420` uses full range of data, but not `YUV420`. Either way, if you need to remove the complaints at the source, do consider the changes mentioned in [this issue](https://github.com/Globotix/usb_cam/issues/3).

#### A ROS Driver for V4L USB Cameras
This package is based off of V4L devices specifically instead of just UVC.

For full documentation, see [the ROS wiki](http://ros.org/wiki/usb_cam).

[Doxygen](http://docs.ros.org/noetic/api/usb_cam/html/) files can be found on the ROS wiki.

### License
usb_cam is released with a BSD license. For full terms and conditions, see the [LICENSE](LICENSE) file.

### Authors
See the [AUTHORS](AUTHORS.md) file for a full list of contributors.
