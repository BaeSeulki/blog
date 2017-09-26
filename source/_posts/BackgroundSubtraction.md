---
title: 基于监控视频的前景目标提取
date: 2017-09-17 04:14:12
categories:
- CV
tags:
- Opencv
---
# 题目
[基于监控的目标检测](http://pan.baidu.com/s/1eSOraIe)
# 准备工作
4天时间，能完成多少是多少吧，然而准备工作是最烦的了，加上之前没有捣弄过，T T  
> 安装opencv
   
`brew install cmake`   
`brew install pkg-config`   
`brew tap homebrew/science`    
`brew install opencv`   
这样就安装好了opencv3.3，不得不说homebrew简直神器！  
然后一些其他库  
`brew install boost`  
然而cmake的时候发生：    
`Boost include path: /usr/local/include  
 Could not find the following Boost libraries: boost_python`  
黑线脸。。。明明都已经  
`sudo chmod -R 777 /usr/local/include`  
`sudo chmod -R 777 /usr/local/lib`  
`brew link boost`  
还居然报错，垃圾。怎么解决呢？看来方向错了，一查原来是没有安装boost-python。  
只好靠`brew install boost-python`弥补一下，其实在装boost的时候`brew install boost --with-python` 就好了。  
自己已经有的环境,`python2.7.13`, `gcc` 。
重新cmake：
* * * 
```shell 
-- BGSLIBRARY WITH PYTHON SUPPORT: ON
-- PYTHON VERSION: 2
-- OpenCV library status:
--     version: 3.3.0
--     libraries: opencv_calib3d;opencv_core;opencv_dnn;opencv_features2d;opencv_flann;opencv_highgui;opencv_imgcodecs;opencv_imgproc;opencv_ml;opencv_objdetect;opencv_photo;opencv_shape;opencv_stitching;opencv_superres;opencv_video;opencv_videoio;opencv_videostab;opencv_aruco;opencv_bgsegm;opencv_bioinspired;opencv_ccalib;opencv_datasets;opencv_dpm;opencv_face;opencv_fuzzy;opencv_img_hash;opencv_line_descriptor;opencv_optflow;opencv_phase_unwrapping;opencv_plot;opencv_reg;opencv_rgbd;opencv_saliency;opencv_stereo;opencv_structured_light;opencv_surface_matching;opencv_text;opencv_tracking;opencv_xfeatures2d;opencv_ximgproc;opencv_xobjdetect;opencv_xphoto
--     include path: /usr/local/include;/usr/local/include/opencv
-- SEARCHING FOR BOOST COMPONENT FOR PYTHON 2
CMake Warning at /usr/local/Cellar/cmake/3.9.2/share/cmake/Modules/FindBoost.cmake:767 (message):
  Imported targets not available for Boost version 106501
Call Stack (most recent call first):
  /usr/local/Cellar/cmake/3.9.2/share/cmake/Modules/FindBoost.cmake:871 (_Boost_COMPONENT_DEPENDENCIES)
  /usr/local/Cellar/cmake/3.9.2/share/cmake/Modules/FindBoost.cmake:1501 (_Boost_MISSING_DEPENDENCIES)
  CMakeLists.txt:94 (find_package)


-- Boost version: 1.65.1
-- Found the following Boost libraries:
--   python
-- Boost library status:
--     version: 106501
--     libraries: /usr/local/lib/libboost_python-mt.dylib
--     include path: /usr/local/include
-- Python library status:
--     executable: /usr/bin/python
--     version: 2.7.10
--     library: /usr/lib/libpython2.7.dylib
--     include path: /usr/include/python2.7
-- NUMPY_INCLUDE_DIR: /Users/zhouyu/Library/Python/2.7/lib/python/site-packages/numpy/core/include
-- Configuring done
-- Generating done
-- Build files have been written to: /Users/zhouyu/Github/bgslibrary/build
```
* * *

成功，wonderful，准备工作告一段落。




