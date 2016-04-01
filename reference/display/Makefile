#/**************************************************************************
# *
# *         Copyright (c) 2005-2014 by iCatch Technology Inc.
# *
# *  This software is copyrighted by and is the property of iCatch
# *  Technology Inc. All rights are reserved by iCatch Technology Inc.
# *  This software may only be used in accordance with the corresponding
# *  license agreement. Any unauthorized use, duplication, distribution,
# *  or disclosure of this software is expressly forbidden.
# *
# *  This Copyright notice MUST not be removed or modified without prior
# *  written consent of iCatch Technology Inc.
# *
# *  iCatch Technology Inc. reserves the right to modify this software
# *  without notice.
# *
# *  iCatch Technology Inc.
# *  19-1, Innovation First Road, Science-Based Industrial Park,
# *  Hsin-Chu, Taiwan.
# *
# *  Author: Anmin Deng
# *
# **************************************************************************/
#init empty simple flavor variables before any include
CFLAGS :=
ASFLAGS :=


HOST_ROOT := ../../..
include $(HOST_ROOT)/host.def
ifndef PLATFORM_PATH
PLATFORM_PATH := $(PLATFORM)
endif
PLATFORM_ROOT := $(HOST_ROOT)/../$(PLATFORM_PATH)
TOOL_PATH := $(HOST_ROOT)/../tool

# output
SRC_DIR   := .
DEST_DIR  := $(HOST_ROOT)/_$(PRJ)
OBJS_PATH := $(DEST_DIR)/_$(PLATFORM_PATH)

# Include the definition of tool chain
include $(PLATFORM_ROOT)/tool_chain.def

#---------------------------------------------------------------------------
# Variable definition:
#   1. Cross-compling tools
#   2. Linker script file
#   3. C complier options
#   4. Assembly compiler options
#   5. Linker options
#---------------------------------------------------------------------------
ifeq (cc,$(CC))
CC   := $(PREFIX)/gcc
AR   := $(PREFIX)/ar
ECHO := echo
endif

ifeq ($(dbg), 1)
GOAL := libdisp_custom_d.a
CFLAGS += -DDBG_FUNC_TRACE_EXT_EN=1
CFLAGS += -DDBG_ASSERT_EXT_EN=1
CFLAGS += -DDBG_PRINT_EXT_EN=1
else
ifeq ($(dbg), 2)
GOAL := libdisp_custom.a
CFLAGS += -DDBG_FUNC_TRACE_EXT_EN=1
CFLAGS += -DDBG_ASSERT_EXT_EN=1
CFLAGS += -DDBG_PRINT_EXT_EN=1
else
GOAL := libdisp_custom.a
CFLAGS += -DDBG_FUNC_TRACE_EXT_EN=0
CFLAGS += -DDBG_ASSERT_EXT_EN=0
CFLAGS += -DDBG_PRINT_EXT_EN=0
endif
endif


ifdef lvl
CFLAGS += -DDBG_PRINT_EXT_LVL=$(lvl)
endif

CFLAGS += -Wall
CFLAGS += -Os
CFLAGS += -G 8
CFLAGS += -ansi
CFLAGS += -I$(DEST_DIR)/include
CFLAGS += -I$(PLATFORM_ROOT)/inc


#---------------------------------------------------------------------------
# Intermediate objects
#---------------------------------------------------------------------------
DEV_OBJS :=
DEV_OBJS += disp_composite_tv_ntsc.o
DEV_OBJS += disp_composite_tv_pal.o
DEV_OBJS += disp_composite_tv_all.o

DEV_OBJS += disp_hdmi_tv_all.o
#DEV_OBJS += disp_hdtv_bt1120_all.o
#DEV_OBJS += disp_hdtv_bt1120_d2_all.o

#DEV_OBJS += disp_auo_a015an04_ups051.o
#DEV_OBJS += disp_auo_a015an04_ups052.o

#DEV_OBJS += disp_gp_gp024QS5_ups052.o
#DEV_OBJS += disp_auo_a025bn01_ups051.o
#DEV_OBJS += disp_auo_a025bn01_ups052.o
#DEV_OBJS += disp_auo_a025bn01_ccir656_w640.o
#DEV_OBJS += disp_auo_a025bn01_yuv_w640.o
#DEV_OBJS += disp_auo_a025bn01_ccir601_ntsc.o
#DEV_OBJS += disp_auo_a025bn01_ccir601_pal.o
#DEV_OBJS += disp_auo_a025bn01_ccir656_ntsc.o
#DEV_OBJS += disp_auo_a025bn01_ccir656_pal.o
#DEV_OBJS += disp_auo_a025bn01_d2_ups051.o
#DEV_OBJS += disp_auo_a025bn01_d2_ups052.o
#DEV_OBJS += disp_auo_a025bn01_d2_ccir601_ntsc.o
#DEV_OBJS += disp_auo_a025bn01_d2_ccir601_pal.o
#DEV_OBJS += disp_auo_a025bn01_d2_ccir656_ntsc.o
#DEV_OBJS += disp_auo_a025bn01_d2_ccir656_pal.o
DEV_OBJS += disp_auo_a030vac01_ups051.o
DEV_OBJS += disp_auo_a030vac01_ups052.o
DEV_OBJS += disp_auo_a030vac01_yuv_w720_l480.o

#DEV_OBJS += disp_auo_a027dn01_ups052.o

DEV_OBJS += disp_gp_gpm1303a0_ups051.o
DEV_OBJS += disp_gp_gpm1303a0_d2_ups051.o
DEV_OBJS += disp_nq_y83482v01_ups051.o
DEV_OBJS += disp_gp_gpm1410a0_ups051.o
#DEV_OBJS += disp_gp_gpm1316b0_dsi_h.o
#DEV_OBJS += disp_gp_gpm1316b0_dsi_v.o
DEV_OBJS += disp_gp_gpg64482qs2_yuv_w640.o

DEV_OBJS += disp_gp_gpm1502_030_ups051.o
DEV_OBJS += disp_gp_gpm1502_030_ups052.o

DEV_OBJS += disp_gp_gpm1502b0_030_ups051.o
DEV_OBJS += disp_gp_gpm1177b1_ups052.o

DEV_OBJS += disp_moto_12m80967a78_dsi1_lcd.o
DEV_OBJS += disp_moto_12m80967a78_dsi1_lcm.o
DEV_OBJS += disp_moto_12m80967a78_dsi2_lcd.o
DEV_OBJS += disp_moto_12m80967a78_dsi2_lcm.o

DEV_OBJS += disp_ss_ams326pm01_ups051.o

#DEV_OBJS += disp_tma_ts027caard02_ups052.o

#DEV_OBJS += disp_tp_td025theb1_ups052.o
#DEV_OBJS += disp_tp_td020theg1_ups052.o
DEV_OBJS += disp_tp_td025theea_ups052.o

#DEV_OBJS += disp_txd_txdt240tq_lcm_h.o
#DEV_OBJS += disp_txd_txdt240tq_lcm_v.o

DEV_OBJS += disp_txd_txdt250c_ups052.o

DEV_OBJS += disp_wd_F9648XF7FLWa_030_ups051.o
DEV_OBJS += disp_wd_F9648XF7FLWa_030_ups052.o

DEV_OBJS += disp_wd_F9648XJ_030_ups051.o
DEV_OBJS += disp_wd_F9648XJ_030_ups052.o
DEV_OBJS += disp_tcs_cogt350_lcm_h.o 
DEV_OBJS += disp_zyw_t2024pd0_lcm_h.o 
DEV_OBJS += disp_dul_GpWt_030_ups051.o

DEV_OBJS += disp_dul_GpWt_030_ups051.o
DEV_OBJS += disp_dummy_one.o


#original rules are list below but have problem. use ugly workaround.
#DEV_OBJS += disp_ana_anx7150.o
#DEV_OBJS += ANX7150_Sys7150.o
#DEV_OBJS += ANX7150_System_Config.o
#DEV_OBJS += EP932_SysController.o
#DEV_OBJS += EP932_SystemConfig.o
#DEV_OBJS += disp_ana_anx7150_dummy.o
#DEV_OBJS += ANX7150_Sys7150_dummy.o
#DEV_OBJS += ANX7150_System_Config_dummy.o
#DEV_OBJS += Disp_EP_EP932_dummy.o
#DEV_OBJS += EP932_SysController_dummy.o
#DEV_OBJS += EP932_SystemConfig_dummy.o
#DEV_OBJS += disp_auo_a024cn03_dummy.o

OBJS := $(DEV_OBJS)

# no optional controller specific objs
#OBJS += disp_xxx.o
#OBJS += disp_yyy.o

#---------------------------------------------------------------------------
# Referring to generic rules
#---------------------------------------------------------------------------
$(eval $(call GEN_GOAL_RULES))

#---------------------------------------------------------------------------
# Private rules
#---------------------------------------------------------------------------
BUILD_DEV_OBJS := $(addprefix $(BUILD_DIR)/,$(DEV_OBJS))

$(BUILD_DEV_OBJS:.o=.d): %:
	@$(MKDIR) $(dir $@)
	@$(CC) $(CFLAGS) -MM -MT '$(@:.d=.o) $@' -o $@ $<

$(BUILD_DEV_OBJS): %:
	$(MSG_SPLIT_LINE)
	$(MSG_COMPILING)
	@$(CC) -c $(CFLAGS) -o $@ $<


define DISP_OPT_RULES
# disp opt upper case
 DISP_OPT_$(1)_$(2) := DISP_$$(shell /bin/sh -c \
		"echo '$(2)' | sed -e 's/\(.*\)/\U\1/'")

 $$(BUILD_DIR)/$(1)_$(2).d: $$(SRC_DIR)/$(1).c
 $$(BUILD_DIR)/$(1)_$(2).o: $$(SRC_DIR)/$(1).c $$(BUILD_DIR)/$(1)_$(2).d
 $$(BUILD_DIR)/$(1)_$(2).d: CFLAGS += -D$$(DISP_OPT_$(1)_$(2))=1
 $$(BUILD_DIR)/$(1)_$(2).o: CFLAGS += -D$$(DISP_OPT_$(1)_$(2))=1

 ifeq ($(3),DEV2)
  $$(BUILD_DIR)/$(1)_d2_$(2).d: $$(SRC_DIR)/$(1).c
  $$(BUILD_DIR)/$(1)_d2_$(2).o: $$(SRC_DIR)/$(1).c $$(BUILD_DIR)/$(1)_d2_$(2).d
  $$(BUILD_DIR)/$(1)_d2_$(2).d: CFLAGS += -D$$(DISP_OPT_$(1)_$(2))=1 -DDISP_DEV_ID=2
  $$(BUILD_DIR)/$(1)_d2_$(2).o: CFLAGS += -D$$(DISP_OPT_$(1)_$(2))=1 -DDISP_DEV_ID=2
 endif
endef

#
# disp_composite_tv.c
#
$(foreach opt,ntsc pal all,$(eval \
	$(call DISP_OPT_RULES,disp_composite_tv,$(opt))))

#
# disp_hdmi_tv.c
#
$(foreach opt,all,$(eval \
	$(call DISP_OPT_RULES,disp_hdmi_tv,$(opt))))

#
# disp_hdtv_bt1120.c
#
$(foreach opt,all,$(eval \
	$(call DISP_OPT_RULES,disp_hdtv_bt1120,$(opt),DEV2)))

#
# disp_auo_a015an04.c
#
$(foreach opt,ups051 ups052,$(eval \
	$(call DISP_OPT_RULES,disp_auo_a015an04,$(opt))))

#
# disp_auo_a025bn01.c
#
$(foreach opt,ups051 ups052 ccir601_ntsc ccir601_pal ccir656_ntsc ccir656_pal,$(eval \
	$(call DISP_OPT_RULES,disp_auo_a025bn01,$(opt),DEV2)))

#
# disp_auo_a027dn01.c
#
$(foreach opt,ups052,$(eval \
	$(call DISP_OPT_RULES,disp_auo_a027dn01,$(opt))))

#
# disp_auo_a030dl01.c
#
$(foreach opt,ups051 ups052,$(eval \
	$(call DISP_OPT_RULES,disp_auo_a030dl01,$(opt),DEV2)))

#
# disp_auo_a030vac01.c
#
$(foreach opt,ups051 ups052 yuv_w720_l480,$(eval \
	$(call DISP_OPT_RULES,disp_auo_a030vac01,$(opt))))



#
# disp_gp_gp024QS5.c
#
$(foreach opt,ups052,$(eval \
	$(call DISP_OPT_RULES,disp_gp_gp024QS5,$(opt))))

#
# disp_gp_gpm1303a0.c
#
$(foreach opt,ups051,$(eval \
	$(call DISP_OPT_RULES,disp_gp_gpm1303a0,$(opt),DEV2)))

#
# disp_nq_y83482v01.c
#
$(foreach opt,ups051,$(eval \
	$(call DISP_OPT_RULES,disp_nq_y83482v01,$(opt))))
	
#
# disp_gp_gpm1410a0.c
#
$(foreach opt,ups051,$(eval \
	$(call DISP_OPT_RULES,disp_gp_gpm1410a0,$(opt))))

#
# disp_gp_gpg64482qs2.c
#
$(foreach opt,ups051 yuv_w640,$(eval \
	$(call DISP_OPT_RULES,disp_gp_gpg64482qs2,$(opt))))

#
# disp_gp_gpm1316b0.c
#
$(foreach opt,dsi_h dsi_v,$(eval \
	$(call DISP_OPT_RULES,disp_gp_gpm1316b0,$(opt))))

#
# disp_gp_gpm1502_030.c
#
$(foreach opt,ups051 ups052,$(eval \
	$(call DISP_OPT_RULES,disp_gp_gpm1502_030,$(opt))))

#
# disp_gp_gpm1177b1.c
#
$(foreach opt, ups052,$(eval \
	$(call DISP_OPT_RULES,disp_gp_gpm1177b1,$(opt))))

#
# disp_gp_gpm1502b0_030.c
#
$(foreach opt,ups051,$(eval \
	$(call DISP_OPT_RULES,disp_gp_gpm1502b0_030,$(opt))))

#
# disp_moto_12m80967a78.c
#
$(foreach opt,dsi1_lcd dsi1_lcm dsi2_lcd dsi2_lcm,$(eval \
	$(call DISP_OPT_RULES,disp_moto_12m80967a78,$(opt))))

#
# disp_ss_ams326pm01.c
#
$(foreach opt,ups051,$(eval \
	$(call DISP_OPT_RULES,disp_ss_ams326pm01,$(opt),DEV2)))

#
# disp_txd_txdt240tq.c
#
$(foreach opt,lcm_h lcm_v,$(eval \
	$(call DISP_OPT_RULES,disp_txd_txdt240tq,$(opt))))

#
# disp_txd_txdt250c.c
#
$(foreach opt,ups052,$(eval \
	$(call DISP_OPT_RULES,disp_txd_txdt250c,$(opt))))

#
# disp_tp_td020theg1.c
#
$(foreach opt,ups052,$(eval \
	$(call DISP_OPT_RULES,disp_tp_td020theg1,$(opt))))

#
# disp_tp_td025theb1.c
#
$(foreach opt,ups052,$(eval \
	$(call DISP_OPT_RULES,disp_tp_td025theb1,$(opt))))

#
# disp_tp_td025theea.c
#
$(foreach opt,ups052,$(eval \
	$(call DISP_OPT_RULES,disp_tp_td025theea,$(opt),DEV2)))

#
# disp_tma_ts027caard02.c
#
$(foreach opt,ups052,$(eval \
	$(call DISP_OPT_RULES,disp_tma_ts027caard02,$(opt))))

#
# disp_wd_F9648XF7FLWa_030.c
#
$(foreach opt,ups051 ups052,$(eval \
	$(call DISP_OPT_RULES,disp_wd_F9648XF7FLWa_030,$(opt))))


#
# disp_wd_F9648XJ_030.c
#
$(foreach opt,ups051 ups052,$(eval \
	$(call DISP_OPT_RULES,disp_wd_F9648XJ_030,$(opt))))

#
# disp_tcs_cogt350.c
#
$(foreach opt,lcm_h,$(eval \
	$(call DISP_OPT_RULES,disp_tcs_cogt350,$(opt))))
	
#
# disp_zyw_t2024pd0.c
#
$(foreach opt,lcm_h,$(eval \
	$(call DISP_OPT_RULES,disp_zyw_t2024pd0,$(opt))))
	
#
# disp_dul_GpWt_030.c
#
$(foreach opt,ups051 ups052,$(eval \
	$(call DISP_OPT_RULES,disp_dul_GpWt_030,$(opt))))
	
#
# disp_dummy.c
#
$(foreach opt,one,$(eval \
	$(call DISP_OPT_RULES,disp_dummy,$(opt))))
	
#
# Ugly workaround for disp_ana_anx7150.c, ANX7150_Sys7150.c,
# ANX7150_System_Config.c, EP932_SysController.c, EP932_SystemConfig.c
#
#
$(foreach opt,dummy,$(eval \
	$(call DISP_OPT_RULES,disp_ana_anx7150,$(opt))))

$(foreach opt,dummy,$(eval \
	$(call DISP_OPT_RULES,ANX7150_Sys7150,$(opt))))

$(foreach opt,dummy,$(eval \
	$(call DISP_OPT_RULES,ANX7150_System_Config,$(opt))))

$(foreach opt,dummy,$(eval \
	$(call DISP_OPT_RULES,Disp_EP_EP932,$(opt))))

$(foreach opt,dummy,$(eval \
	$(call DISP_OPT_RULES,EP932_SysController,$(opt))))

$(foreach opt,dummy,$(eval \
	$(call DISP_OPT_RULES,EP932_SystemConfig,$(opt))))

$(foreach opt,dummy,$(eval \
	$(call DISP_OPT_RULES,disp_auo_a024cn03,$(opt))))

