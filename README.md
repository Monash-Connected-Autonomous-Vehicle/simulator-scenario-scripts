# simulator-scenario-scripts

## Build Information

Autoware is built in the temp_autoware directory

`
cd temp_autoware/autoware
`

![img.png](img.png)

Make sure you source the ROS package

`
source /opt/ros/humble/setup.bash
`

...and source the setup shell script

`
source install/setup.bash
`

![img_2.png](img_2.png)

## Launching Autoware

Found this link, seems quite useful
https://autowarefoundation.github.io/autoware-documentation/main/how-to-guides/integrating-autoware/launch-autoware/

## Manual Planning Simulator
To launch the manual planning simulator with a sample map, model and sensor

`
ros2 launch autoware_launch planning_simulator.launch.xml map_path:=$HOME/autoware_map/sample-map-planning vehicle_model:=sample_vehicle sensor_model:=sample_sensor_kit
`

# Scenarios

A sample scenario is stored in the sample.yaml file at the following location
/home/mcav/temp_autoware/autoware/src/simulator/scenario_simulator/test_runner/scenario_test_runner/scenario/sample.yaml

A similar file is also present in this repo.

Run using: 

`
ros2 launch scenario_test_runner scenario_test_runner.launch.py \
  architecture_type:=awf/universe/20240605 \
  record:=false \
  scenario:='$(find-pkg-share scenario_test_runner)/scenario/sample.yaml' \
  sensor_model:=sample_sensor_kit \
  vehicle_model:=sample_vehicle
  frame_rate:=10
`
* changed the command from suggested awf/universe to awf/universe/20240605 due to having multiple versions

    ![img_1.png](img_1.png)

## Building our Scenarios
