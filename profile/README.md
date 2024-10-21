# Rubberverse.xyz

Organization full of various Dockerfile(s) and some other for-fun stuff powering (or not) [my own personal site](https://rubberverse.xyz)

Welcome to teh Rubberverse, I guess.


## Image/Dockerfile quality

Should be pretty okay-ish. Most of software runs about out of stock configuration with only difference being the configuration filles and where stuff is stored is in a comfortable `/app` directory.

Aiming for pure software feel with comfort, along with each image running as an unprivileged user by default inside the container. Mostly no weird modifications to the actual software, no usage of supervisors unless needed, and no root user switching unless for comfort (as a seperate image)

Granted some Dockerfile parts could've been done in a more sane way (ex. no `cd` during build) but I want to squish everything into a single layer which is why stuff is done the way it is. Eventually all is going to be improved as I learn down the line.


## Compatibility

All images are ran and tested with Podman. I don't really care about Docker so... there are probably better images if you use that.


## Where your images are published?

For now, only on my [Dockerhub](https://hub.docker.com/repositories/mrrubberducky), I'll bring GitHub Container Registry into play if anybody wants it on there.
