<a id="record-the-screen"></a>

# Record the screen

You can record a video of your screen. The video either captures your whole screen or a selected region. It’s saved as a WebM or MP4 video file.

1. Press `PrintScr` and switch to Record Screen.

   Alternatively, press `Ctrl+Alt+Shift+R`.
2. Select what to record:
   * Selection records a screen region.
   * Screen records your whole screen.
3. Click Capture or press `Enter`.

   A red indicator in the top panel shows that you’re recording and for how long.
4. To stop the recording, click the red indicator in the top panel.
5. Find the recording in the `Videos/Screencasts` folder in your home directory.

## Hardware acceleration for improved recording

To improve performance and save battery life on laptops, you can enable hardware acceleration for video encoding.

By default, your screen recording relies on your CPU. This might cause skipped frames or higher resource usage, even if you don’t immediately notice stuttering. Many computers have dedicated hardware for video encoding using VA-API (Video Acceleration API), which is more efficient.

* You can select third-party drivers in the Ubuntu installer to enable hardware acceleration.
* On any Ubuntu release that’s already installed and running, install packages that provide hardware acceleration:
  `$ ``sudo apt install gstreamer1.0-plugins-bad`

#### NOTE
Certain GPU models and drivers don’t support VA-API. With these, screen recording will still rely on the CPU even after installing the extra packages.
