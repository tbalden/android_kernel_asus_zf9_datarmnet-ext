#By default build for CLD
RMNET_APS_SELECT := CONFIG_RMNET_APS=m
KBUILD_OPTIONS += $(RMNET_APS_SELECT)
KBUILD_OPTIONS += $(KBUILD_EXTRA) # Extra config if any
KBUILD_EXTRA_SYMBOLS := $(ANDROID_BUILD_TOP)/out/vendor/qcom/opensource/datarmnet/core/Module.symvers
KBUILD_OPTIONS += RMNET_CORE_INC_DIR=$(ANDROID_BUILD_TOP)/vendor/qcom/opensource/datarmnet/core/

M ?= $(shell pwd)

all:
	$(MAKE) -C $(KERNEL_SRC) M=$(M) modules $(KBUILD_OPTIONS)

modules_install:
	$(MAKE) INSTALL_MOD_STRIP=1 -C $(KERNEL_SRC) M=$(M) modules_install

clean:
	$(MAKE) -C $(KERNEL_SRC) M=$(M) clean
