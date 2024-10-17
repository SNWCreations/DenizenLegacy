# DenizenLegacy

This project brings back the support of
older Minecraft versions for Denizen.

This branch is for Minecraft 1.20.1,
 and **ONLY** compatible with [Mohist](https://github.com/MohistMC/Mohist).

Developed for [The SRS Project](https://github.com/TheSRSProject)
because our tech stack is based on Minecraft 1.20.1.

This is based on (my fork of)
[GitPatcher](https://github.com/zml2008/gitpatcher),
it makes us maintain the patches easier.
_See my fork of it there: [Link](https://github.com/SNWCreations/gitpatcher)_

## Supported versions

This repository contains support for the following Minecraft versions:
* 1.20.1

**Did not find the version you want?**

You'll have to do backport by yourself, just like what this
repository did. **DO NOT ASK ME TO ADD MORE SUPPORT.**
I only consider adding more support for a random MC version when I'm bored.
To be honest, there's really no need to stop at a particular patch version
if possible.

## Compiling

Run `git submodule update --init` if you forget to
add `--recurse-submodules` flag while cloning this repository,
this make sure the upstream repository exists so
the patch would be able to be applied.

Run `gradlew applyPatches` to apply the patches
to the upstream project.

Now the patched project is ready at `target` folder,
use Maven to compile it, and you're good to go.

## Work with this project

This project (excluding the upstream part) is only
used to patch the upstream using our own patches,
so changes to the project should be commited to
the `target` submodule.

The `upstream` submodule is only used to sync with
the upstream. **DO NOT MODIFY IT.**

When updating the project is needed,
run `git pull` in `upstream` submodule to sync
with upstream, and then run `gradlew applyPatches`
to apply patches, solve the conflict and then use Git CLI to
continue the process of applying patch, if any.

When your patches are commited to the target repository,
run `gradlew makePatches` to export them.

After that, your patches are ready to be commited to
the bootstrap repository (this project).

If you're working with several Minecraft versions at
the same time, **DO NOT** merge the different branches
as the patches will break, Git will just tell you "patch
does not apply, did you hand edit the patch"?

## Disclaimer

This project is unaffiliated with
The Denizen Script Team and will **NOT** be supported by them.

**DO NOT EXPECT THIS ALWAYS WORK, NO WARRANTY.**
If it does not work, you'll have to deal with the
exceptions by yourself. Although issues are welcome,
but I am still just focus on 1.20.1 unless my project
has moved to other Minecraft version.

## License

Copyright (C) 2024 SNWCreations.

This project and the patches to the upstream project
inside this project are licensed under MIT License,
see `LICENSE` file in this repository
for the license content.
