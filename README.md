# kinect2_bagplayer
Republisher extra kinect2 topics from a reduced recorded set.
See also a similar package here:
[Kinect2 Playback](https://github.com/si-machines/data_logger_bag/wiki/Kinect2-Playback)

Let's say your rosbag has ALL the kinect2 topics, so it's huge and cannot be played properly.
We can safely filter some of those extra topics from the rosbag by:
```bash
rosbag filter  S1-T1.1-A1.bag  SMALL_S1-T1.1-A1-timeless.bag   "('kinect2' not  in topic ) or (topic == '/robot5/sensors/kinect2/hd/image_color' or  topic == '/robot5/sensors/kinect2/hd/camera_info' or topic == '/robot5/sensors/kinect2/sd/image_depth' or  topic == '/robot5/sensors/kinect2/sd/camera_info' )"
```

Now you can replay the leaner version and use the provided launchfile to "recreate" the removed topics.
