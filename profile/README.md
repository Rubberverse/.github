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

## Can I has your dockerfile? :3

Ye sure, go ahead they're just glorified shell scripts shoved into a file anyways. Wouldn't mind if you referenced it but I won't care if you don't. Do as you wish, I just select MIT because that's the only license I know from top of my finger and I'm not a lawyer.

## Free support??//

Stuff I make here are mostly for my own use, it's great if it works for you but don't expect stellar, top of the line support. You can create a GitHub issue and maybe I'll take a lookie but I won't really bother fixing it unless it impacts me personally. I'll probably tackle onto it when I'm bored.
