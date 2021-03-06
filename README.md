# persistent-home-docker
This repository provides a minimum template configuration so that the container's user home folder is mirrored in the host, making its files persistent.

---
## Usage

1. Clone (or download) this repository:
```
git clone git@github.com:hbaqueiro/persistent-home-docker.git
```
2. Adapt `Dockerfile` to your needs.
In this example, configuration was set up to work with ROS2 Foxy and Gazebo. You
may want to rename the image in both `Dockerfile` and `run-devel.bash`.

3. Run `run-devel.bash` (make sure it has execute permission):

```
chmod +x run-devel.bash
./run-devel.bash
```

The `home` folder of this repository will mirror and persist all the data of the container's home folder.

---
## Tip

I find extremely useful to keep a docker monitor running in a separate terminal
showing the images, the running and the stopped containers.

For that, add the
following to your host's `~/.bash_aliases`:

```
alias docker_status='echo === IMAGES =============== && docker images && echo && \
             echo === RUNNING CONTAINERS === && docker ps && echo && \
             echo === ALL CONTAINERS ======= && docker ps -a'
alias docker_monitor='while true; clear; do docker_status; sleep 5; done'
```
Then:
```
source ~/.bash_aliases
docker_monitor
```

---
## References
- http://wiki.ros.org/docker/Tutorials/GUI

