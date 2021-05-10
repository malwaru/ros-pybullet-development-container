FROM osrf/ros:noetic-desktop-full

USER root
RUN apt-get update && apt install -y python3-pip python3-catkin-tools ros-noetic-cv-bridge git wget
RUN pip3 install pybullet opencv-python osrf-pycommon

ARG UNAME=ros_user
ARG WS_DIR=/home/$UNAME/catkin_ws
ARG UID=1000
ARG GID=1000
RUN groupadd -g $GID -o $UNAME
RUN useradd -m -s /bin/bash -N -u $UID $UNAME && \
    adduser $UNAME sudo && \
    echo "$UNAME ALL=(ALL:ALL) NOPASSWD:ALL" | sudo tee /etc/sudoers.d/$UNAME && \
    mkdir -p $WS_DIR/src &&\
    chown $UNAME:$GID -R $WS_DIR

USER $UNAME
WORKDIR $WS_DIR/src

RUN git clone https://github.com/oscar-lima/pybullet_ros.git
WORKDIR $WS_DIR
RUN catkin init
RUN catkin config --extend /opt/ros/noetic/
RUN catkin build
RUN echo "source $WS_DIR/devel/setup.bash" >> /home/$UNAME/.bashrc

CMD /bin/bash