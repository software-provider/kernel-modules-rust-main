ifneq ($(KERNELRELEASE),)

# In kbuild context
mem_layout-objs := main.o
obj-m := mem_layout.o

else
# In normal make context
KERNELDIR ?= /lib/modules/$(shell uname -r)/build
PWD := $(shell pwd)

.PHONY: modules
modules:
	$(MAKE) -C $(KERNELDIR) M=$(PWD) modules

.PHONY: clean
clean:
	$(MAKE) -C $(KERNELDIR) M=$(PWD) clean
	rm -f libmain.rmeta

endif
