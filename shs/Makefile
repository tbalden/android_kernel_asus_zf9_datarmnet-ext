KERNEL_SRC ?= /lib/modules/$(shell uname -r)/build

KBUILD_OPTIONS := RMNET_SHS_ROOT=$(PWD)
KBUILD_OPTIONS += MODNAME?=rmnet_shs
KBUILD_EXTRA_SYMBOLS := $(ANDROID_BUILD_TOP)/out/vendor/qcom/opensource/datarmnet/core/Module.symvers
KBUILD_OPTIONS += RMNET_CORE_INC_DIR=$(ANDROID_BUILD_TOP)/vendor/qcom/opensource/datarmnet/core/
M ?= $(shell pwd)

all:
	$(MAKE) -C $(KERNEL_SRC) M=$(M) modules $(KBUILD_OPTIONS) $(KBUILD_EXTRA_SYMBOLS)

modules_install:
	$(MAKE) INSTALL_MOD_STRIP=1 -C $(KERNEL_SRC) M=$(M) modules_install

clean:
	$(MAKE) -C $(KERNEL_SRC) M=$(M) clean
