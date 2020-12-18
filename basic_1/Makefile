ifneq ($(KERNELRELEASE),)
obj-m +=  hello17.o
obj-m +=  hello27.o
ccflags-y += -I$(obj)/inc
ccflags-y += -g
else
# normal makefile
KDIR ?= /lib/modules/`uname -r`/build
default:
	$(MAKE) -C $(KDIR) M=$$PWD
	cp hello17.ko hello17.ko.unstripped
	cp hello27.ko hello27.ko.unstripped
	$(CROSS_COMPILE)strip -g hello17.ko hello27.ko
clean:
	$(MAKE) -C $(KDIR) M=$$PWD clean
endif
