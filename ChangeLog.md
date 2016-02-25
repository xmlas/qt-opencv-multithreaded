# v1.3.3 (22nd December 2013) #
  * NEW FEATURE: Application window can now be resized freely (image will scale accordingly). UI has been re-arranged to support this feature.
  * NEW FEATURE: Application can now handle any camera resolution (window size will auto adjust on connect).
  * NEW FEATURE: Add menu item to toggle full screen on/off.
  * Cursor display: value in square brackets now displays cursor "pixel coordinates".
  * Increase smooth image operation kernel ranges.
  * Increase dilate and erode no. of iteration ranges.

# v1.3.2 (24th July 2013) #
  * NEW FEATURE: Resolution can optionally be set (via OpenCV call) when connecting to the camera.
  * BUGFIX: Fixed bug on stream disconnect which caused frame processing to occur in other opened streams in a sync wait-state.
  * BUGFIX: Added wakeAll() call to allow camera to disconnect if in a wait-state.
  * Capture thread now checks if a frame is available before grabbing.
  * Processing thread optimized to have less conditional checks during image processing.
  * Renamed "Exit" menu item to "Quit".
  * `CameraView` objects are now stored in an accessible map in `MainWindow`.
  * `ImageBuffer` is now derived from a Buffer template class.
  * Changed `CameraView` from QMainWindow to QWidget (for Mac OS/X compatibility reasons).
  * Removed menu from `CameraView` and replaced with context menu which appears on   right-click of frame.

# v1.3.1 (13th May 2013) #
  * New features:
    * UI: Added number of captured frames display.
    * UI: Moved number of frames processed label to be next to FPS label.
    * Stream synchronization: Multiple streams can be processed in sync on a frame-by-frame basis.
    * Shared image buffer: Allows threads access to image buffers from other streams.
    * (Related to previous) Frame processing can be disabled per stream. This allows a `ProcessingThread` to grab (and process) frames from multiple streams.
    * Scale to fit frame: Frame can optionally be scaled to fit the entire window (i.e. when a ROI is set or a low resolution is being used).
  * All references to cameraID in source code removed. A stream is now uniquely identified by the Device Number (i.e. the device number of the connected camera).
  * Statistics information from both the processing and capture threads now uses a dedicated signal/slot with a common structure to hold the data.

# v1.3.0 (3rd April 2013) #
  * New features:
    * Application now supports simultaneous capturing and processing from multiple cameras.
    * Display of number of frames processed.
  * Code completely re-structured (and redundant code removed).
  * Code is fully compatible/compilable with Qt 5.

# v1.21 (3rd February 2012) #
  * New features:
    * Capture and processing thread priority can be chosen at run-time.
    * Option to drop frame if image/frame buffer is full.
    * Display of the cursor position relative to the ROI.
  * GUI re-arranged and neatened.
  * Minor code restructuring/cleanup:
    * Method of setting/resetting ROI has been simplified.
    * Setting/resetting the ROI does now **not** cause a frame to be skipped from processing.
    * Camera connect and disconnect methods have been simplified.

# v1.20 (12th July 2011) #
  * Utilizes the new OpenCV 2.x C++ API.
  * After setting a ROI, the resulting region is now centered in the display frame.
  * Minor code restructuring/cleanup.

# v1.12 (23rd February 2011) #
  * Method of setting/resetting ROI on mouse events changed.

# v1.11 (8th February 2011) #
  * Processing settings dialog has been changed to a more compact tabbed-dialog.

# v1.10 (30th January 2011) #
  * Processing settings can now be changed during runtime.
  * All drawing when setting the ROI is now performed using QPainter instead of OpenCV's cvRectangle().

# v1.00 (19th January 2011) #
  * First release.