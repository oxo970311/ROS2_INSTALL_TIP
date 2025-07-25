<!--
ROS2 VPN

# ros2 install url
# https://makingrobot.tistory.com/159

sudo apt install network-manager
nmcli dev wifi list
nmcli dev wifi connect "WIFI_ID" password "WIFI_PW"
nmcli con show --active

sudo apt install tailscale
sudo tailscale up    # sudo tailscale down
https://login.tailscale.com/…..
tailscale ip -4
tailscale status

sudo apt install ros-humble-cyclonedds
cyclonedds-discovery-server    #server choice
cyclonedds-discovery-server --address 0.0.0.0 --port 5000


               RASPBERRY_PI                                                 PC

sudo nano ~/.bashrc                                    sudo nano ~/.bashrc
export RMW_IMPLEMENTATION=rmw_cyclonedds_cpp           export RMW_IMPLEMENTATION=rmw_cyclonedds_cpp 
export ROS_DISCOVERY_SERVER='[PC_IP]:5000'             export ROS_DISCOVERY_SERVER='[RASPBERRY_PI_IP]:5000'
export ROS_DOMAIN_ID=n                                 export ROS_DOMAIN_ID=n    # n must be same value
export ROS_LOCALHOST_ONLY=0                            export ROS_LOCALHOST_ONLY=0

source /opt/ros/humble/setup.bash                      source /opt/ros/humble/setup.bash
ros2 run demo_nodes_cpp talker                         ros2 run demo_nodes_cpp listener
-->
