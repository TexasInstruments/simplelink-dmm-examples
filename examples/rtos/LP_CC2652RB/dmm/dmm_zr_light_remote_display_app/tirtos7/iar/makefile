COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR ?= $(abspath ../../../../../../..)

include $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/imports.mak

CC = "$(IAR_ARMCOMPILER)/bin/iccarm"
LNK = "$(IAR_ARMCOMPILER)/bin/ilinkarm"

SYSCFG_CMD_STUB = $(SYSCONFIG_TOOL) --compiler iar --product $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/.metadata/product.json
SYSCFG_FILES := $(shell $(SYSCFG_CMD_STUB) --listGeneratedFiles --listReferencedFiles --output . ../../tirtos7/dmm_zr_light_remote_display.syscfg)

SYSCFG_C_FILES = $(filter %.c,$(SYSCFG_FILES))
SYSCFG_H_FILES = $(filter %.h,$(SYSCFG_FILES))
SYSCFG_OPT_FILES = $(filter %.opt,$(SYSCFG_FILES))

OBJECTS = application_main.obj software_stacks_ti15_4stack_radio_configuration_mac_user_config.obj application_zr_light_StackApi_zstackapi.obj application_zr_light_StackApi_zstackstartup.obj application_cui_cui.obj application_zr_light_util_util_timer.obj application_zr_light_util_mac_util.obj application_zr_light_ui_zcl_sampleapps_ui.obj application_zr_light_zcl_samplelight.obj application_zr_light_zcl_samplelight_data.obj application_zr_light_per_test.obj application_ble_remote_display_remote_display.obj dmm_dmm_priority_ble_zigbee_zr.obj drivers_ecc_ECCROMCC26XX.obj software_stacks_ble_stack_profiles_light_gatt_profile.obj software_stacks_ble_stack_profiles_provisioning_gatt_profile.obj software_stacks_ble_stack_icall_ble_rd_ble_user_config.obj software_stacks_zstack_stack_task_zstacktask.obj software_stacks_zstack_common_zcl_zcl.obj software_stacks_zstack_common_zcl_zcl_port.obj software_stacks_zstack_common_zcl_zcl_general.obj software_stacks_zstack_common_zcl_zcl_green_power.obj software_stacks_zstack_common_zcl_zcl_ha.obj software_stacks_zstack_common_zcl_zcl_diagnostic.obj software_stacks_zstack_af_af.obj software_stacks_zstack_bdb_bdb.obj software_stacks_zstack_bdb_bdb_finding_and_binding.obj software_stacks_zstack_bdb_bdb_reporting.obj software_stacks_zstack_bdb_bdb_touchlink.obj software_stacks_zstack_bdb_bdb_touchlink_initiator.obj software_stacks_zstack_bdb_bdb_touchlink_target.obj software_stacks_zstack_common_touchlink_bdb_tl_commissioning.obj software_stacks_zstack_common_touchlink_touchlink_initiator_app.obj software_stacks_zstack_common_touchlink_touchlink_target_app.obj software_stacks_zstack_common_gp_gp_common.obj software_stacks_zstack_common_gp_gp_proxy_table.obj software_stacks_zstack_common_gp_gp_proxy.obj software_stacks_zstack_nwk_nwk_globals.obj software_stacks_zstack_nwk_stub_aps.obj software_stacks_zstack_nwk_binding_table.obj software_stacks_zstack_osal_port_osal_port.obj software_stacks_zstack_osal_port_osal_port_timers.obj software_stacks_zstack_osal_port_osal_nv.obj software_stacks_zstack_sys_zdiags.obj software_stacks_zstack_sys_zglobals.obj software_stacks_zstack_zdo_zd_app.obj software_stacks_zstack_zdo_zd_config.obj software_stacks_zstack_zdo_zd_nwk_mgr.obj software_stacks_zstack_zdo_zd_object.obj software_stacks_zstack_zdo_zd_profile.obj software_stacks_zstack_zdo_zd_sec_mgr.obj software_stacks_zstack_zmac_zmac.obj software_stacks_zstack_zmac_zmac_cb.obj application_ble_remote_display_startup_osal_icall_ble.obj application_ble_remote_display_startup_rom_init.obj application_ble_remote_display_startup_ble_user_config_stack.obj software_stacks_ble_stack_rosc_rcosc_calibration.obj drivers_nv_nvocmp.obj drivers_nv_crc.obj software_stacks_ble_stack_icall_icall_cc2650.obj software_stacks_ble_stack_icall_icall_user_config.obj software_stacks_ble_stack_icall_ble_icall_api_lite.obj software_stacks_ble_stack_icall_ble_icall_hci_tl.obj software_stacks_ble_stack_profiles_devinfoservice.obj software_stacks_ble_stack_profiles_gattservapp_util.obj software_stacks_ble_stack_icall_icall.obj application_ble_remote_display_util_util.obj software_stacks_ti15_4stack_mac_high_level_mac_cfg.obj software_stacks_ti15_4stack_mac_low_level_mac_settings.obj software_stacks_ti15_4stack_mac_services_saddr.obj software_stacks_ti15_4stack_mac_hal_target_itm.obj software_stacks_ti15_4stack_mac_low_level_mac_activity.obj $(patsubst %.c,%.obj,$(notdir $(SYSCFG_C_FILES)))
NAME = dmm_zr_light_remote_display_app

CFLAGS += -I../.. \
    -I. \
    $(addprefix -f,$(SYSCFG_OPT_FILES)) \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$ \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/dmm/ \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/dmm/apps/ \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/posix \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/posix/iar \
    -f../../TOOLS/defines/dmm_zr_light_remote_display_app.opts \
    -f../../TOOLS/defines/f8wrouter.opts \
    -I../../ \
    -I../../ble_remote_display \
    -I../../StackApi \
    -I../../syscfg \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ti154stack/common/util \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ti154stack \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ti154stack/common \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ti154stack/common/osal_port \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ti154stack/common/boards \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ti154stack/common/boards/CC1352R1_LAUNCHXL \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ti154stack/common/inc \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ble5stack/heapmgr \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ble5stack/services/src/aes \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/common/nv \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/zstack/apps/light \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/dmm/light_profile/ \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/dmm/provisioning_profile/ \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/dmm/apps/common/zstack/source/ble_remote_display/app/ \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/dmm/apps/common/zstack/source/ \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/zstack/config \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/common/cui \
    -DxUSE_ITM_DBG \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/zstack/startup \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/zstack/mt \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/zstack/stack/api \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/zstack/stack/af \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/zstack/stack/bdb \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/zstack/stack/bdb/touchlinkapp \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/zstack/stack/gp \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/zstack/stack/nwk \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/zstack/stack/sec \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/zstack/stack/sys \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/zstack/stack/zcl \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/zstack/stack/zdo \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/zstack/zmac \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/zstack/zmac/f8w \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/zstack/stack/ui \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/zstack/osal \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/zstack/per_test \
    -DTIMAC_ROM_IMAGE_BUILD \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ti154stack/fh \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ti154stack/high_level \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ti154stack/inc \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ti154stack/rom \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ti154stack/inc/cc13xx \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ti154stack/low_level/cc13xx \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ti154stack/low_level/cc13xx/2_4g \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ti154stack/tracer \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ti154stack/hal/crypto \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ti154stack/hal/rf \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ti154stack/services/sdata \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ti154stack/services/saddr \
    -f../../TOOLS/build_components.opt \
    -f../../TOOLS/factory_config.opt \
    -DFLASH_ROM_BUILD \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ble5stack/common/cc26xx/rcosc \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ble5stack/common/cc26xx/npi/stack \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ble5stack/controller/cc26xx/inc \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ble5stack/inc \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ble5stack/rom \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ble5stack/common/cc26xx \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ble5stack/icall/inc \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ble5stack/hal/src/common \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ble5stack/hal/src/inc \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ble5stack/hal/src/target/_common \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ble5stack/profiles/dev_info \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ble5stack/profiles/simple_profile \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ble5stack/icall/src/ \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ble5stack/icall/src/inc \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ble5stack/osal/src/inc \
    -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/common/cc26xx \
     -DBoard_EXCLUDE_NVS_EXTERNAL_FLASH \
     -DCC2652RB \
     -DNVOCMP_NVPAGES=2 \
    " -I$(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source" \
    -Ohz \
     -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/devices/cc13x2_cc26x2 \
     -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/devices/cc13x2_cc26x2/inc \
     -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/devices/cc13x2_cc26x2/rf_patches \
     -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/devices/cc13x2_cc26x2/driverlib \
     -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/posix \
     -I$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/posix/iar \
    -DTIRTOS7_SUPPORT \
     -DHEAPMGR_CONFIG=0x80 \
     -DHEAPMGR_SIZE=0x00 \
    "-I$(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/kernel/tirtos7/packages" \
    "-I$(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/posix/iar" \
    --debug \
    --silent \
    -e \
    --aeabi \
    --thumb \
    --diag_suppress=Pa050 \
    --cpu Cortex-M4 \
    --fpu=VFPv4_sp \
    --vla

LFLAGS +=  -f$COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR$/source/ti/ti154stack/rom/lib/iar/timac_rom_PG2_0_rom_api_linker.icf \
    --config_def=FLASH_ROM_BUILD=2 \
    " -L$(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source" \
    "-L$(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/kernel/tirtos7/packages" \
    -fti_utils_build_linker.cmd.genlibs \
    "$(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/devices/cc13x2_cc26x2/driverlib/bin/iar/driverlib.lib" \
    --config ../../tirtos7/iar/cc26xx_app_and_stack_agama_tirtos7.icf \
    --map "$(NAME).map" \
    --silent \
    --semihosting=iar_breakpoint \
    --cpu=Cortex-M4 \
    --fpu=VFPv4_sp

all: postbuild

.PHONY: postbuild
postbuild: $(NAME).out
	ielftool.exe --ihex --verbose "./$(NAME).out" "./$(NAME).hex"

.INTERMEDIATE: syscfg
$(SYSCFG_FILES): syscfg
	@ echo generation complete

syscfg: ../../tirtos7/dmm_zr_light_remote_display.syscfg
	@ echo Generating configuration files...
	@ $(SYSCFG_CMD_STUB) --output $(@D) $<

define C_RULE
$(basename $(notdir $(1))).obj: $(1) $(SYSCFG_H_FILES)
	@ echo Building $$@
	@ $(CC) $(CFLAGS) $$< -o $$@
endef

$(foreach c_file,$(SYSCFG_C_FILES),$(eval $(call C_RULE,$(c_file))))

application_main.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/dmm/apps/common/zstack/source/main.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_ti15_4stack_radio_configuration_mac_user_config.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/ti154stack/common/boards/mac_user_config.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

application_zr_light_StackApi_zstackapi.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/api/zstackapi.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

application_zr_light_StackApi_zstackstartup.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/startup/zstackstartup.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

application_cui_cui.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/common/cui/cui.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

application_zr_light_util_util_timer.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/ti154stack/common/util/util_timer.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

application_zr_light_util_mac_util.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/ti154stack/common/util/mac_util.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

application_zr_light_ui_zcl_sampleapps_ui.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/ui/zcl_sampleapps_ui.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

application_zr_light_zcl_samplelight.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/apps/light/zcl_samplelight.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

application_zr_light_zcl_samplelight_data.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/apps/light/zcl_samplelight_data.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

application_zr_light_per_test.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/per_test/per_test.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

application_ble_remote_display_remote_display.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/dmm/apps/common/zstack/source/ble_remote_display/app/remote_display.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

dmm_dmm_priority_ble_zigbee_zr.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/dmm/dmm_priority_ble_zigbee_zr.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

drivers_ecc_ECCROMCC26XX.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/common/cc26xx/ecc/ECCROMCC26XX.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_ble_stack_profiles_light_gatt_profile.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/dmm/light_profile/cc26xx/light_gatt_profile.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_ble_stack_profiles_provisioning_gatt_profile.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/dmm/provisioning_profile/cc26xx/provisioning_gatt_profile.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_ble_stack_icall_ble_rd_ble_user_config.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/dmm/apps/common/zstack/source/ble_remote_display/rd_ble_user_config.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_stack_task_zstacktask.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/api/zstacktask.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_common_zcl_zcl.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/zcl/zcl.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_common_zcl_zcl_port.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/zcl/zcl_port.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_common_zcl_zcl_general.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/zcl/zcl_general.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_common_zcl_zcl_green_power.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/zcl/zcl_green_power.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_common_zcl_zcl_ha.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/zcl/zcl_ha.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_common_zcl_zcl_diagnostic.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/zcl/zcl_diagnostic.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_af_af.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/af/af.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_bdb_bdb.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/bdb/bdb.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_bdb_bdb_finding_and_binding.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/bdb/bdb_finding_and_binding.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_bdb_bdb_reporting.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/bdb/bdb_reporting.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_bdb_bdb_touchlink.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/bdb/bdb_touchlink.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_bdb_bdb_touchlink_initiator.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/bdb/bdb_touchlink_initiator.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_bdb_bdb_touchlink_target.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/bdb/bdb_touchlink_target.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_common_touchlink_bdb_tl_commissioning.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/bdb/touchlinkapp/bdb_tl_commissioning.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_common_touchlink_touchlink_initiator_app.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/bdb/touchlinkapp/touchlink_initiator_app.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_common_touchlink_touchlink_target_app.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/bdb/touchlinkapp/touchlink_target_app.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_common_gp_gp_common.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/gp/gp_common.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_common_gp_gp_proxy_table.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/gp/gp_proxy_table.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_common_gp_gp_proxy.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/gp/gp_proxy.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_nwk_nwk_globals.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/nwk/nwk_globals.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_nwk_stub_aps.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/nwk/stub_aps.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_nwk_binding_table.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/nwk/binding_table.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_osal_port_osal_port.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/ti154stack/common/osal_port/osal_port_posix/osal_port.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_osal_port_osal_port_timers.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/ti154stack/common/osal_port/osal_port_posix/osal_port_timers.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_osal_port_osal_nv.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/osal/osal_nv.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_sys_zdiags.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/sys/zdiags.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_sys_zglobals.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/sys/zglobals.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_zdo_zd_app.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/zdo/zd_app.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_zdo_zd_config.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/zdo/zd_config.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_zdo_zd_nwk_mgr.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/zdo/zd_nwk_mgr.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_zdo_zd_object.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/zdo/zd_object.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_zdo_zd_profile.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/zdo/zd_profile.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_zdo_zd_sec_mgr.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/stack/zdo/zd_sec_mgr.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_zmac_zmac.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/zmac/f8w/zmac.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_zstack_zmac_zmac_cb.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/zstack/zmac/f8w/zmac_cb.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

application_ble_remote_display_startup_osal_icall_ble.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/dmm/apps/common/ble_remote_display/stack/osal_icall_ble.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

application_ble_remote_display_startup_rom_init.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/ble5stack/rom/agama_r1/rom_init.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

application_ble_remote_display_startup_ble_user_config_stack.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/ble5stack/icall/stack/ble_user_config_stack.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_ble_stack_rosc_rcosc_calibration.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/ble5stack/common/cc26xx/rcosc/rcosc_calibration.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

drivers_nv_nvocmp.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/common/nv/nvocmp.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

drivers_nv_crc.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/common/nv/crc.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_ble_stack_icall_icall_cc2650.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/ble5stack/icall/src/icall_cc2650.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_ble_stack_icall_icall_user_config.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/ble5stack/icall/src/icall_user_config.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_ble_stack_icall_ble_icall_api_lite.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/ble5stack/icall/app/icall_api_lite.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_ble_stack_icall_ble_icall_hci_tl.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/ble5stack/icall/app/icall_hci_tl.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_ble_stack_profiles_devinfoservice.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/ble5stack/profiles/dev_info/cc26xx/devinfoservice.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_ble_stack_profiles_gattservapp_util.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/ble5stack/host/gattservapp_util.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_ble_stack_icall_icall.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/ble5stack/icall/src/icall.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

application_ble_remote_display_util_util.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/ble5stack/common/cc26xx/util.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_ti15_4stack_mac_high_level_mac_cfg.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/ti154stack/high_level/mac_cfg.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_ti15_4stack_mac_low_level_mac_settings.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/ti154stack/low_level/cc13xx/mac_settings.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_ti15_4stack_mac_services_saddr.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/ti154stack/services/saddr/saddr.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_ti15_4stack_mac_hal_target_itm.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/ti154stack/tracer/itm.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

software_stacks_ti15_4stack_mac_low_level_mac_activity.obj: $(COM_TI_SIMPLELINK_CC13XX_CC26XX_SDK_INSTALL_DIR)/source/ti/ti154stack/low_level/cc13xx/mac_activity.c $(SYSCFG_H_FILES)
	@ echo Building $@
	@ $(CC) $(CFLAGS) $< -o $@

$(NAME).out: $(OBJECTS)
	@ echo linking $@
	@ $(LNK)  $(OBJECTS)  $(LFLAGS) -o $(NAME).out

clean:
	@ echo Cleaning...
	@ $(RM) $(OBJECTS) > $(DEVNULL) 2>&1
	@ $(RM) $(NAME).out > $(DEVNULL) 2>&1
	@ $(RM) $(NAME).map > $(DEVNULL) 2>&1
	@ $(RM) $(SYSCFG_FILES)> $(DEVNULL) 2>&1
