# 3D Systems Touch Containerized ROS2 Interface
**Authors:** Aidan Kirwin, Steven Yang | 
**Platform:** ROS 2 Humble,  Ubuntu 22.04

---

## Opening and Building the Workspace

1. Install Docker Engine (https://docs.docker.com/engine/install/ubuntu/)
2. Clone this repository

### 1. Set up the Docker container(s)

The Docker container has the following dependencies: ROS2 Humble, TouchDriver2022_04_04, OpenHaptics 3.4.0 |

```bash
cd HapticDevice
docker compose build --progress=plain haptic_device
docker compose up haptic_device
docker exec -it haptic_device bash
```

Note that there is a `docker-compose.yml` file.

### 2. Build the workspace(s)

```bash
colcon build --symlink-install --cmake-args -DCMAKE_BUILD_TYPE=Release
source install/setup.bash
```

> **Note:** You must run `source install/setup.bash` in every new terminal, or add it to your `~/.bashrc`.

---

## Running the Workspace

```bash
ros2 launch haptic_device haptic_device.launch.py
```


