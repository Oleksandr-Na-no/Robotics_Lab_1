## How to Run the Simulation

### 1. Prepare the Environment

Open the Docker container from the [robotics_lpnu](https://www.google.com/search?q=https://github.com/RybOlya/robotics_lpnu) repository.

> **Note:** You need to navigate to the `robotics_lpnu/` folder (`cd robotics_lpnu/`) and run the `./scripts/cmd run` command in your Ubuntu terminal.

### 2. Set Up the Workspace

Inside the container, run the following commands to source the ROS environment, clone the project, and navigate to the working directory:

```bash
source /opt/ros/jazzy/setup.bash
cd /opt/ws/src/code
git clone https://github.com/Oleksandr-Na-no/Robotics_Lab_1
cd /opt/ws/src/code/Robotics_Lab_1

```

### 3. Launch the Simulation

Start the Gazebo simulation by running:

```bash
gz sim worlds/robot.sdf

```

### 4. Configure Gazebo and Run

Once the simulation window opens:

* In the **top right corner**, click the **3 dots (⋮)** tab and select **Key Publisher**.
* In the **bottom left corner**, press the **RUN** button to start the physics engine.

---

## Controls & Useful Commands

### Keyboard Control

Make sure the Key Publisher is active. You can now use the **W, S, A, D** keys to control the movement of the robot.

### See all topics

In another terminal, list the available topics:

```bash
gz topic -l

```

### View Lidar Data

To observe the Lidar output directly in the terminal, run:

```bash
gz topic -e -t /lidar

```

### Send Movement Commands

You can also send movement commands manually via another terminal. Here is an example:

```bash
gz topic -t "/cmd_vel" -m gz.msgs.Twist -p "linear: {x: 0.5}, angular: {z: 0.2}"

```
