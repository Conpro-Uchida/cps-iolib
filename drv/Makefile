obj-m := cps-iolib.o

#self-build
#CC=gcc
#KERNELDIR ?= /lib/modules/$(shell uname -r)/build 
PWD       := $(shell pwd)

EXTRA_CFLAGS	:= -DDEBUG=0

#cross build 
CROSS_COMPILE=arm-linux-gnueabi-
ARCH=arm
KERNELDIR ?= /home/contec/workspace/sdk/CPS_SDK/kernel #target kernel source path

all:
	$(MAKE) ARCH=$(ARCH) CROSS_COMPILE=$(CROSS_COMPILE) -C $(KERNELDIR) M=$(PWD) modules

modules_install:
	$(MAKE) -C $(KERNELDIR) M=$(PWD) modules_install

clean:
	rm -rf *.o *~ core .depend .*.cmd *.ko *.mod.c .tmp_versions vtty Module.symvers modules.order 
