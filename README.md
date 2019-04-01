# iozone

This tree is cloned from http://iozone.org .

The makefile was modified, the target **linux-VE** was added such that it allows to build native *iozone* for the NEC SX-Aurora TSUBASA vector engine (VE).

The SX-Aurora VE is a vector accelerator CPU on a PCIe card that is offloading I/O to the host machine.
Therefore normal I/O system calls are handled on the linux host machine, even if invoked inside the
native VE code. While *iozone* for the host would just test the characteristics of the Filesyste to Host transfer,
with *iozone-VE* we can easily test the behaviour of programs doing I/O from inside the
VE, i.e. the full chain:

Filesystem <-> Linux Host <-> Vector Engine


## Build

On a machine with installed Vector Engine and SDK (compilers): clone this repository:
```sh
git clone https://github.com/efocht/iozone-ve.git
```
then build the application(s):
```sh
cd iozone-ve
make linux-VE
```


