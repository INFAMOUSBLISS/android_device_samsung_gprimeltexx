default: all

KBUILD_OPTIONS := WLAN_ROOT=$(WLAN_ROOT)
KBUILD_OPTIONS += MODNAME=wlan

all::
	$(MAKE) -C $(KERNEL_SOURCE) $(KBUILD_OPTIONS) $(EXTRA_CFLAGS) ARCH=$(ARCH) \
		SUBDIRS=$(CURDIR) CROSS_COMPILE=$(CROSS_COMPILE) modules

modules_install:
	$(MAKE) INSTALL_MOD_STRIP=1 -C $(KERNEL_SRC) M=$(WLAN_ROOT) modules_install

clean::
	find -type f -iname '*.o' | xargs rm || true
	find -type f -iname '*.ko' | xargs rm || true 
	find -type f -iname '*.mod.o' | xargs rm || true 
	find -type f -iname '*.mod.c' | xargs rm || true 
	find -type f -iname '*.cmd' | xargs rm  || true 
	find -type f -iname '*.o.cmd' | xargs rm || true 
	rm -f *.o *.ko *.mod.c *.mod.o *~ .*.cmd Module.symvers || true
	rm -rf .tmp_versions


