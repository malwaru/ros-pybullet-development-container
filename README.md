# ros-pybullet-development-container

1. First build the container image with `docker build -f .devcontainer/Dockerfile -t pybullet_ros .` 
3. Install the extension `ms-vscode-remote.remote-containers`
2. Open the folder `row-pybullet-development-container` with vscode. 
3. If an alert pops up about the folder containing a Dev Container configuration use this to open the folder in the container -> Done
1. Otherwise open the command pallete and type: `Rebuild and Reopen in Container`
1. Everything should start now according to the configuration.

The `src/` folder is mounted directly into the dev container and should be used for `ros` and `pybullet` development.


Note:

For NVIDIA graphic cards follow the instructions on the link given below. You must do this before buidling the image and no need to add the bash script. It is already taken care of in the .yml file

http://wiki.ros.org/docker/Tutorials/Hardware%20Acceleration

