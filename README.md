cuda-ssh
========
Ubuntu Core 16.04 + [CUDA8+](http://www.nvidia.com/object/cuda_home_new.html) + SSH server + X server (for NVIDIA Visual Profiler).

Requirements
------------

- [NVIDIA Docker](https://github.com/NVIDIA/nvidia-docker) - see [requirements](https://github.com/NVIDIA/nvidia-docker/wiki/CUDA#requirements) for more details.

Build
-----
Include password.txt with the password for sshd (by default this is "password").

Usage
-----
Use NVIDIA Docker: ``nvidia-docker run -dP acerja2/cuda-ssh``.

The default password should be changed. To do so start up a container and then run `docker exec <id> bash -c "echo 'root:<password>' | chpasswd"`.

For automatically mapping a SSH port use ``nvidia-docker run -dP acerja2/cuda-ssh`` and `docker port <id>` to retrieve the port.
For specifying the port manually use ``nvidia-docker run -d -p <port>:22 acerja2/cuda-ssh``.
The shell can be entered as usual using ``nvidia-docker run -it acerja2/cuda-ssh bash``.

The NVIDIA Visual Profiler (`nvvp`) can be accessed with an X client, after having run ssh with the `-X` flag.

For more information on CUDA on Docker, see the repo where this was forked from [repo readme](https://github.com/Kaixhin/dockerfiles#cuda).

Citation
--------
These modifications were based on work done by Kaixhin in his dockerfiles repository. If you like it, you can refer back to his source repository for many other dockerfiles encapsulating a lot of tools.

If you find this useful in research please consider [citing Kaixhin's work](https://github.com/Kaixhin/dockerfiles/blob/master/CITATION.md).