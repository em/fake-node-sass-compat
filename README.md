node-sass is a dead project, doesn't build on m1

the sass.js alone should work with anything, but we have an old project that internally uses node-sass

originally we had some wacky yarn resolution tricks that forced node-sass to point to sass.js and avoided the m1 build problem

when trying to upgrade to yarn 3, those resolution hacks didn't work anymore, yarn 3 complaints that the name of the package doesn't match

this is an attempt to workaround that by just snapshotting sass.js but naming the package node-sass.

this way we can simply do `resolutions: {"node-sass": "https://github.com/em/fake-node-sass-compat"}`
