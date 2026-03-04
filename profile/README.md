# Organization for things I've made, or maybe just want to have here.

The site in question being [rubberverse.xyz](https://rubberverse.xyz)

## Image / Containerfile quality

Should be alright. I usually focus less on caching and more on ensuring everything is done inside single layer to optimize final filesize a bit more, sometimes works, sometimes not.

My aim is to also make them as secure as I can, so there will be weird restrictive permissions on files, containers themselves will run as a rootless user, and in some cases the runner image will be `scratch` - so no shell utilities, package managers etc. just the raw binary of the program. Also under one directory which is `/app`.

I tend to avoid inits such as su-exec, gosu as they don't really make sense in grand scheme of things. Your container still runs as `0` and remains as `0` even if it forks off to another user. Virtually no security benefit, only done for comfort. You can achieve ownership of directories by using `:U` flag on Podman which will make container process chown it and mount it - if you want the same files to be usable by x user then just add `UserNS=keep-id:uid=your_uid,gid=your_gid,size=your_uid+1` but that will lower your security by a bit since then it will run the container as your users namespace vs. randomized.

## Compatibility

Images should run on anything that supports containers and OCI images I guess. I suppose even in Kubernetes it should run fine since they're rootless by default.

## Maintainability

In most cases you can just git clone a repo and follow instructions to build latest versions of the software. I use `public.ecr.aws` during build time since they have way more relaxed pull limits so you won't risk running into mystical rate limit errors.

## Where your images are published?

GitHub Container Registry (ghcr.io/rubberverse)

Used to be on Docker Hub but they kept giving and taking away stuff all the time while trying to upsell you that expensive monthly plan, not to mention these new ratelimits are tragic. 

## Can I has your dockerfile? :3

Ye sure, go ahead they're just glorified shell scripts shoved into a file anyways. Wouldn't mind if you gave a little shoutout to me but I won't care if you won't. referenced it but I won't be sad if you don't. Do as you wish, I just select MIT because that's the only license I know from top of my finger and I'm not a lawyer.

## Free support??//

Stuff I make here are mostly for my own use, it's great if it works for you but don't expect stellar, top of the line support. You can create a GitHub issue and maybe I'll take a lookie but I won't really bother fixing it unless it impacts me personally. I'll probably tackle onto it when I'm bored. You can hit me up via e-mail to ask questions, some peeps done that before.

## Is there like example configurations or Quadlet deployments somewhere?

You can see them in my personal [GitHub](https://github.com/MrRubberDucky/Homelab) page thingy, whatever.
