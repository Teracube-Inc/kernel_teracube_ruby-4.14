#subdir-ccflags-y += -Werror
ccflags-y += -I$(srctree)/drivers/misc/mediatek/include/mt-plat/
ccflags-y += -I$(srctree)/drivers/input/touchscreen/mediatek
ccflags-y += -I$(srctree)/drivers/misc/mediatek/include/mt-plat/$(MTK_PLATFORM)/include

# In case the platform does NOT support this type of sensors
obj-y   +=  mtk_tpd.o
obj-y   +=  tpd_button.o
obj-y   +=  tpd_calibrate.o
obj-y   +=  tpd_debug.o
obj-y   +=  tpd_default.o
obj-y   +=  tpd_misc.o
obj-y   +=  tpd_setting.o
obj-$(CONFIG_TOUCHSCREEN_MTK_SOLOMON)	+=  SOLOMON/
obj-$(CONFIG_TOUCHSCREEN_MTK_FOCALTECH_TS)	+=  focaltech_touch/

# Stoneoim:wangfei on: Wed, 12 Nov 2014 21:06:42 +0800
# for compatible the old style ,so use CUSTOM_KERNEL_IMGSENSOR
project_name:=$(shell echo $(CONFIG_VANZO_INNER_PROJECT_NAME))
ifneq ($(project_name),)

ifneq ($(strip $(BOOT_LOGO)),)
boot_logo := $(shell echo $(BOOT_LOGO) | tr '[a-z]' '[A-Z]')
$(info boot_logo = $(boot_logo))
CONFIG_CUSTOM_BOOT_LOGO:=$(boot_logo)
endif

subdir-ccflags-y += -D$(CONFIG_CUSTOM_BOOT_LOGO)

ifneq ($(strip $(CUSTOM_KERNEL_TOUCHPANEL)),)
CONFIG_CUSTOM_KERNEL_TOUCHPANEL:=$(CUSTOM_KERNEL_TOUCHPANEL)
endif

custom_kernel_touchpanel:= $(addsuffix /, $(shell echo $(CONFIG_CUSTOM_KERNEL_TOUCHPANEL)))

$(info "custom_kernel_touchpanel:$(custom_kernel_touchpanel)")
obj-y += $(custom_kernel_touchpanel)
else
# End of Stoneoim:wangfei

obj-$(CONFIG_TOUCHSCREEN_MTK_GT1151)	+=  GT1151/
obj-$(CONFIG_TOUCHSCREEN_MTK_GT911)	+=  GT911/
obj-$(CONFIG_TOUCHSCREEN_MTK_GSLX680)	+=  gslX680/
obj-$(CONFIG_TOUCHSCREEN_MTK_NT36xxx)	+=  NT36xxx/
obj-$(CONFIG_TOUCHSCREEN_MTK_GT9XX_LM)	+=  GT9XX_LM/
obj-$(CONFIG_TOUCHSCREEN_FT5X26)	+=  FT5X26/
obj-$(CONFIG_TOUCHSCREEN_MTK_GT5688)	+=  GT5688/
obj-$(CONFIG_TOUCHSCREEN_HIMAX_I2C)	+=  hxchipset/
obj-$(CONFIG_TOUCHSCREEN_MTK_FOCALTECH_FHD)	+=  focaltech_fhd_touch/
obj-$(CONFIG_TOUCHSCREEN_MTK_GSL1691)	+=  GSL1691/
obj-$(CONFIG_TOUCHSCREEN_MTK_FT8006U)	+=  FT8006U/
obj-$(CONFIG_TOUCHSCREEN_MTK_FT8719)	+=  FT8719/
obj-$(CONFIG_TOUCHSCREEN_MTK_GT1XX)	+=  GT1XX/
obj-$(CONFIG_TOUCHSCREEN_MTK_CHIPONE)	+=  chipone-tddi/
obj-$(CONFIG_TOUCHSCREEN_MTK_FOCALTECH_MULTITYPE)	+=  focaltech_multiType/
obj-$(CONFIG_TOUCHSCREEN_MTK_FT8719_I2C)        +=  ft8719_i2c/
obj-$(CONFIG_TOUCHSCREEN_HIMAX_HX83112)        +=  hx83112/
obj-$(CONFIG_TOUCHSCREEN_MTK_ILITEK)        +=  ilitek/
obj-$(CONFIG_TOUCHSCREEN_MTK_MSG22XX)        +=  msg22xx/
obj-$(CONFIG_TOUCHSCREEN_MTK_PARADE)        +=  parade/

endif
