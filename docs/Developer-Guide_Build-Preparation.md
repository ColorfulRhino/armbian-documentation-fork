# Building Armbian

## What do I need?

- x86/x64/aarch64 machine running any OS; at least 4G RAM, SSD, quad core (recommended),
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads) or similar virtualization software **(highly recommended with a minimum of 25GB hard disk space for the virtual disk image)**
- **The officially supported** compilation environment is [Ubuntu Jammy 22.04.x amd64](https://www.releases.ubuntu.com/jammy/) **only!**
- `binfmt_misc` kernel module (some *ubuntu-cloud* images do not have this module.  Switch to a generic kernel if that is the case.)
- installed basic system, OpenSSH and Samba (optional)
- no spaces in full path to the build script location allowed
- superuser rights (configured `sudo` or root shell).

Not officially supported build environments from community contributions:

- [Docker](Developer-Guide_Building-with-Docker.md) environment is also supported for building kernels and full OS images,
- [Multipass](https://gist.github.com/atomic77/7633fcdbf99dca80f31fd6d64bfd0565)

Please note that system requirements (both hardware and OS/software) may differ depending on the build environment (Docker, Virtualbox, native).

## How to start?

### Native and VirtualBox environments:

Login as root and run:

```bash
apt-get -y -qq install git  
git clone --depth=1 --branch=main https://github.com/armbian/build  
cd build  
```

Run the script

	./compile.sh

Make sure that full path to the build script **does not contain spaces**.


<iframe width="607" height="342" src="https://www.youtube.com/embed/kQcEFsXEJEE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Providing build configuration

After the first run of `compile.sh` a new configuration file `config-example.conf` and symlink `config-default.conf` will be created.
You may edit it to your needs or create different configuration files using it as a template.

Alternatively you can supply options as command line parameters to compile.sh.
Example:

    ./compile.sh BOARD=cubietruck BRANCH=current RELEASE=jammy

Note: Option `BUILD_ALL` cannot be set to "yes" via command line parameter.  
Note: Names for `BOARD` can be found [here](https://github.com/armbian/build/tree/main/config/boards) by looking at file names. Example: OrangePi 4 = **orangepi4.conf** = `BOARD=orangepi4`

### Base and descendant configuration

You can create one base configuration (`config-base.conf`) and use this in descendant config (`config-edge.conf`). Three parameters (*BRANCH*, *RELEASE*, *COMPRESS_OUTPUTIMAGE*) will be overwritten.

```
. ./config-base.conf  
  
BRANCH="edge"  
RELEASE="bullseye"  
COMPRESS_OUTPUTIMAGE="sha,gz"  
```

## Using GitHub actions

If you do not own the proper equipment to build images on your own, you can try to use our [official GitHub action](https://github.com/marketplace/actions/rebuild-armbian).

## Using alternate armbian builder repos and branches

By default, armbian-builder assumes working from `main` of `https://github.com/armbian/build.git`.  If you are working from your own repo / branch, `touch .ignore_changes` will cause armbian-builder to not attempt a repo checkout.

## Executing any bash statement

Currently, invoking compile.sh will run a monotonous task of building all the components into a final image.

In some situation, especially when developing with Kernel or U-Boot, it is handy to run a portion of that great task like:

```
        # using default profile  
        ./compile.sh 'fetch_from_repo "$BOOTSOURCE" "$BOOTDIR" "$BOOTBRANCH" "yes"'  
        ./compile.sh 'compile_uboot'  
```

You can also dump the variable:

```
        # using profile of `userpatches/config-my.conf`  
        ./compile.sh my 'echo $SRC/cache/sources/$BOOTSOURCEDIR'  
```

NOTE: please use single quotes to keep the `$VAR` from early expansion in the command line shell.
