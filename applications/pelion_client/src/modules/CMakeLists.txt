#
# Copyright (c) 2021 Nordic Semiconductor ASA
#
# SPDX-License-Identifier: LicenseRef-Nordic-5-Clause
#

target_sources(app PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/pelion.cpp)
target_sources(app PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/pelion_fcc.cpp)

target_sources_ifdef(CONFIG_PELION_CLIENT_POWER_MANAGER_ENABLE
		     app PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/power_manager.c)

target_sources_ifdef(CONFIG_PELION_CLIENT_OMA_STOPWATCH
		     app PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/oma_stopwatch.cpp)

target_sources_ifdef(CONFIG_PELION_CLIENT_OMA_DIGITAL_INPUT
		     app PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/oma_digital_input.cpp)

target_sources_ifdef(CONFIG_BOOTLOADER_MCUBOOT
		     app PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/dfu.c)

target_sources_ifdef(CONFIG_CAF_LEDS
		     app PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/led_state.c)

target_sources_ifdef(CONFIG_LTE_LINK_CONTROL
		     app PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/net_lte.c)

target_sources_ifdef(CONFIG_NET_L2_OPENTHREAD
		     app PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/net_ot.c)

target_sources_ifdef(CONFIG_PELION_CLIENT_FACTORY_RESET_REQUEST_ENABLE
		     app PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/factory_reset_request.c)
