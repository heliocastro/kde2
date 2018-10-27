**KDE Restoration Project - KDE 2.2.2**

This is an Software Engineering Archeology work. The intention is to keep original KDE 2
working as along as possible in modern architectures ( Unix and Linux only for now )

Small premises are taken to go with this port:
- Keep the original code as original as possible
- Replace current BuildSystem for a modern one. The actual choice was Cmake since i do
know it better and current KDE uses it

The current status:

**Qt2** is done with some remarks:
- There's a issue as Qt2 didn't recognize ARGB visuals on thos times ( of course ! ), so thanks to Gustavo Boiko that
  found the issue. So, if you do intend to run software like Qt designer, export this on command line:
  `XLIB_SKIP_ARGB_VISUALS=1`
- Compilation depends on byacc. One of the sources are not ported to modern bison/flex. Thanks to @EXl for pointing this
  out

**kdelibs** is done with some remarks:
- arts is not compiled yet. It is my nemesis since i worked at Conectiva several years ago and still a pain. Help
  welcome
- Documentation is not generated. This is secondary and wil be dealt after kdebase
- Install part is done, but is not 100% proved if is done properly
- libtool porting "should" work, but then, not properly tested.
- MOst software can compiled directo from the super repo, but to test unfortunately we need to run dcop and have install
  directory properly setted. This will be preperly test when kdebase port start ( soon i hope, crossing my fingers).

**Building:**

- Clone the super repo: `git clone --recursive git@github.com:heliocastro/kde2.git`
- Enter the directory: `cd kde2`
- Create an non source build dir ( i usually use build ): `mkdir build`
- Run cmake: `cmake ..`

My default compiler is Clang on Fedora Linux 28 at this moment

**Ubuntu Dependencies ( from 16.04 and beyond)**

```bash
sudo apt install bison byacc cmake flex freeglut3-dev libacl1-dev libasound2-dev libbz2-dev libfreetype-dev libgl1-mesa-dev libjpeg-dev libltdl-dev libmng-dev libpcre3-dev libtiff5-dev libxft2-dev libxml2-dev libxmu-dev libxslt-dev pkg-config 
```

I will thanks any help, been clear that this is probably a uselles project, but has some meaning for me at least.

Again thanks to:

**Gustavo Boiko** - @boiko

@EXL
