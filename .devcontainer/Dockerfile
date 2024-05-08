FROM ros:iron

RUN apt-get update \
    && apt-get install -y sudo git pip python3-vcstool curl iputils-ping ros-$ROS_DISTRO-moveit ros-$ROS_DISTRO-slam-toolbox ros-$ROS_DISTRO-ros2-control ros-$ROS_DISTRO-robot-state-publisher ros-$ROS_DISTRO-joint-state-publisher-gui ros-$ROS_DISTRO-ros2-control ros-$ROS_DISTRO-ros2-controllers\
    && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME

# Install Rustup
RUN curl https://sh.rustup.rs -sSf | sh -s -- -y

# Add user to video group to allow access to webcam
RUN usermod --append --groups video $USERNAME

# Rosdep update
ADD ./custom_sources.list /etc/ros/rosdep/sources.list.d/0_custom.list
RUN rosdep update

# Source the ROS setup file
RUN echo "source /opt/ros/${ROS_DISTRO}/setup.bash" >> /etc/profile
