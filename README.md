# Environment
- Ubuntu 18.04
- OpenCV 3.2
- Eigen 3.3.4
- ROS melodic
- docker2

# RUN
```sh
xhost +local:root
```

# BUild Tips
- Eigen
```sh
$pkg-config --modversion eigen3
3.3.4
```
- OpenCV
```
dpkg -l | grep libopencv
$pkg-config --modversion opencv
3.2.0
```
- Error: usleep
```sh
ORB_SLAM2/Examples/Stereo/stereo_kitti.cc:107:13: error: 'usleep' was not declared in this scope
             usleep((T-ttrack)*1e6);
             ^~~~~~
```
Solution:

Add this to the related files.
```cpp
#include<unistd.h>
```

- error: ``XDG_RUNTIME_DIR`` not set in the environment.
```sh
error: XDG_RUNTIME_DIR not set in the environment.
libGL error: No matching fbConfigs or visuals found
libGL error: failed to load driver: swrast
X11 Error: BadMatch (invalid parameter attributes)
X11 Error: BadValue (integer parameter out of range for operation)
New map created with 718 points
terminate called after throwing an instance of 'std::runtime_error'
  what():  Pangolin X11: Failed to create an OpenGL context
Aborted (core dumped)
```


