

<a href='http://qt-opencv-multithreaded.googlecode.com/svn/wiki/qt-opencv-multithreaded-1.3.3_1.png'><img src='http://qt-opencv-multithreaded.googlecode.com/svn/wiki/qt-opencv-multithreaded-1.3.3_1.png' width='268' height='313' /></a> <a href='http://qt-opencv-multithreaded.googlecode.com/svn/wiki/qt-opencv-multithreaded-1.3.3_2.png'><img src='http://qt-opencv-multithreaded.googlecode.com/svn/wiki/qt-opencv-multithreaded-1.3.3_2.png' width='268' height='313' /></a> <a href='http://qt-opencv-multithreaded.googlecode.com/svn/wiki/qt-opencv-multithreaded-1.3.3_3.png'><img src='http://qt-opencv-multithreaded.googlecode.com/svn/wiki/qt-opencv-multithreaded-1.3.3_3.png' width='268' height='313' /></a>

# Description #
This relatively simple multithreaded application can be easily modified to suit the needs of your next Qt GUI-based computer vision project using OpenCV.

**Important:** Please be aware of the Qt license types. See [here](http://qt.digia.com/Product/Licensing/).

# Introduction #
Any application that must perform multiple parallel tasks can benefit from multithreading. Multithreading can provide a solution to the more common problem of simply keeping the interface attractive and responsive while the program is busy. With the increasing popularity of multi-core processors, in not just desktops, but also high-end embedded systems, multithreading can improve not just response times, but also runtimes.

A typical OpenCV application would normally execute code in a large "while" loop that first captures a frame from the camera and then performs image processing on it. This can result in a low frame processing throughput (as well as dropped frames) especially if the image processing is quite complex.

In contrast, this application takes advantage of multithreading to allow frames to be captured from the camera while _at the same time_ performing image processing. In other words, once a frame has been captured from the camera, the application does not have to wait until image processing is performed on that frame before it starts capturing a new frame - instead a new frame is captured, added to a FIFO queue and is processed a short time later.

Of course, another advantage of this application is that it uses Qt, a cross-platform application and UI framework, thus allowing you to create highly user-friendly computer vision applications for a wide range of platforms.

# Examples #
_Projects/products/research using this application as a base:_

**Control Testbed**, _Monash University, Australia_: [Video](http://www.youtube.com/watch?v=f_Ax93E_f1M)

**Developing a Computer Vision Based Sudoku Solver**, _Swiss German University, Indonesia_: [Paper](http://www.sgu.ac.id/library/garuda/swf/MT/2012/Sendy.swf)

**Developing Auto Charging Mechanism on a SCARA Robot Using Vision**, _Swiss German University, Indonesia_: [Paper](http://www.sgu.ac.id/library/thesisdetail.php?id=11108034)

**Developing an Eggshell Inspection System with Computer Vision**, _Swiss German University, Indonesia_: [Paper](http://www.sgu.ac.id/library/thesisdetail.php?id=1-1108-028)

**MultiCV: A computer vision software infrastructure**: [BitBucket](https://bitbucket.org/sfraniatte/multicv) [GitHub](https://github.com/citiZenStef/MultiCV)

**Realtime Video Magnification**: [GitHub](https://github.com/tschnz/Realtime-Video-Magnification)

_<Please contact me if you would like your project created using this application linked here.>_

# Features #
See [Change Log](https://code.google.com/p/qt-opencv-multithreaded/wiki/ChangeLog).
  * Interactive Qt-based GUI (Qt 5).
  * Utilizes the new OpenCV 2.x C++ API.
  * **(NEW)** Multi-camera support: Process frames from multiple cameras simultaneously.
  * **(NEW)** Stream synchronization: Multiple streams can be processed in sync on a frame-by-frame basis.
  * **(NEW)** Shared image buffer: Allows threads access to image buffers from other streams.
  * **(NEW)** Scale to fit frame: Frame can optionally be scaled to fit the entire window (i.e. when a ROI is set or a low resolution is being used).
  * **(NEW)** Resolution can optionally be set (via OpenCV call) when connecting to the camera.
  * **(NEW)** Application can now handle any camera resolution (window size will auto adjust on connect).
  * **(NEW)** Application window can now be resized freely (image will scale accordingly).
  * Small memory footprint (typically <30MB when one camera is connected).
  * Dedicated thread to capture frames from camera.
  * Dedicated thread to perform image processing on captured frames.
  * Thread priorities can be chosen at run-time.
  * Includes function to perform the required conversion from the OpenCV **Mat** format to Qt's **QImage** format.
  * Ability to choose image buffer size and camera device number at run-time.
  * Option to drop frame if image/frame buffer is full.
  * Ability to clear image buffer while the capture and processing threads are running.
  * Ability to set the "region of interest" (ROI) interactively with the aid of a mouse.
  * Graphical representation of image buffer status (% full).
  * Capture rate and processing rate (in FPS) display.
  * **(NEW)** Number of frames captured and processed display.
  * Camera information (device number and resolution) display.
  * Region of interest (ROI) information display.
  * Mouse cursor position display (including pixel position display).
  * Several in-built _(and user-settable)_ OpenCV functions to assess multithreading performance:
    * Grayscale conversion
    * Smooth (Blur, Gaussian, Median)
    * Dilate
    * Erode
    * Flip
    * Canny edge detection

# [Documentation](http://code.google.com/p/qt-opencv-multithreaded/wiki/Documentation) #

# News #
  * **1st June 2014:** Documentation updated (installation instructions for Ubuntu 14.04 + OpenCV 2.4.9 + Qt 5.3.0 combination).
  * **22nd December 2013:** v1.3.3 released. See [Downloads](http://code.google.com/p/qt-opencv-multithreaded/downloads/list) and [Change Log](https://code.google.com/p/qt-opencv-multithreaded/wiki/ChangeLog).
  * **24th July 2013:** v1.3.2 released. See [Downloads](http://code.google.com/p/qt-opencv-multithreaded/downloads/list) and [Change Log](https://code.google.com/p/qt-opencv-multithreaded/wiki/ChangeLog).
  * **13th May 2013:** v1.3.1 released. See [Downloads](http://code.google.com/p/qt-opencv-multithreaded/downloads/list) and [Change Log](https://code.google.com/p/qt-opencv-multithreaded/wiki/ChangeLog).
  * **25th April 2013:** Documentation updated (installation instructions updated for OpenCV 2.4.5, Qt 5.0.2 and Ubuntu 13.04).
  * **3rd April 2013:** v1.3.0 released. See [Downloads](http://code.google.com/p/qt-opencv-multithreaded/downloads/list). Documentation updated (installation instructions updated for OpenCV 2.4.4, Qt 5.0.1 and Ubuntu 13.04).
  * **9th July 2012:** Documentation updated (installation instructions updated for OpenCV 2.4.2). Patched ov534 driver updated to support Linux kernel 3.2.0 (as supplied with Ubuntu 12.04 LTS).
  * **5th May 2012:** Documentation updated (installation instructions for Ubuntu 12.04 + OpenCV 2.4.0 combination).
  * **3rd February 2012:** v1.21 released. See [Downloads](http://code.google.com/p/qt-opencv-multithreaded/downloads/list).
    * Added features:
      * Capture and processing thread priority can be chosen at run-time.
      * Option to drop frame if image/frame buffer is full.
      * Display of the cursor position relative to the ROI.
    * GUI re-arranged and neatened.
    * Minor code restructuring/cleanup:
      * Method of setting/resetting ROI has been simplified.
      * Setting/resetting the ROI does now **not** cause a frame to be skipped from processing.
      * Camera connect and disconnect methods have been simplified.
  * **25th July 2011:** Documentation updated.
  * **12th July 2011:** v1.20 released. See [Downloads](http://code.google.com/p/qt-opencv-multithreaded/downloads/list).
    * Utilizes the new OpenCV 2.x C++ API.
    * After setting a ROI, the resulting region is now centered in the display frame.
    * Minor code restructuring/cleanup.
  * **23rd February 2011:** v1.12 released. See [Downloads](http://code.google.com/p/qt-opencv-multithreaded/downloads/list).
    * Method of setting/resetting ROI on mouse events changed.
  * **8th February 2011:** v1.11 released. See [Downloads](http://code.google.com/p/qt-opencv-multithreaded/downloads/list).
    * Processing settings dialog has been changed to a more compact tabbed-dialog.
  * **30th January 2011:** v1.10 released. See [Downloads](http://code.google.com/p/qt-opencv-multithreaded/downloads/list).
    * Processing settings can now be changed during runtime.
    * All drawing when setting the ROI is now performed using QPainter instead of OpenCV's cvRectangle().
  * **19th January 2011:** v1.00 released. See [Downloads](http://code.google.com/p/qt-opencv-multithreaded/downloads/list).

# Latest SVN Changes #
<wiki:gadget url="http://google-code-feed-gadget.googlecode.com/svn/trunk/gadget.xml" up\_feeds="https://code.google.com/feeds/p/qt-opencv-multithreaded/svnchanges/basic" up\_defer="true" width="800"/>

# Support #
Please report all bugs and issues [here](http://code.google.com/p/qt-opencv-multithreaded/issues/list).

Please [contact me](http://code.google.com/u/nickdademo/) if you have any questions/suggestions/comments regarding this program.