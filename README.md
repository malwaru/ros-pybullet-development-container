# ros-pybullet-development-container

1. First build the container image with `docker build -f .devcontainer/Dockerfile -t pybullet_ros .` 
3. Install the extension `ms-vscode-remote.remote-containers`
2. Open the folder `ros-pybullet-development-container` with vscode. 
3. If an alert pops up about the folder containing a Dev Container configuration use this to open the folder in the container -> Done
1. Otherwise open the command pallete and type: `Rebuild and Reopen in Container`
1. Everything should start now according to the configuration.

The `src/` folder is mounted directly into the dev container and should be used for `ros` and `pybullet` development

Note:

To use NVIDIA graphics card install the nvidia-docker2 by following the instructions in the Setting up NVIDIA Container Toolkit¶ section of the following link

1. Make sure you have done a docker pull of nvidia/cuda  
2. You have CUDA supported graphics card
3. In "Additional drivers" you have chosen the Nvidia driver version 510(Required for installing the Nvidia drivers correctly) 
4. The instructions in http://wiki.ros.org/docker/Tutorials/Hardware%20Acceleration shoudl be followed.Which means following nvidia-docker2 steps
	4.1 Installing the nvidia-docker2
		Which means installing the nvidia driver 
		4.1.1 Follow the instruction on the following link for this. The package manager method was tested and worked 
	
		Link: https://docs.nvidia.com/datacenter/tesla/tesla-installation-notes/index.html

		4.1.2 Proceed to post installtion steps given in link below 
		
		Link: https://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html#post-installation-actions

	4.2 Editing the DockerFile accorind to instructions on http://wiki.ros.org/docker/Tutorials/Hardware%20Acceleration 

	4.3 Replace the bash script functins with the .yaml file 

More information could be found at  

https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html 
