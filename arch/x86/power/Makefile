# SPDX-License-Identifier: GPL-2.0

# __restore_processor_state() restores %gs after S3 resume and so should not
# itself be stack-protected
CFLAGS_cpu.o	:= -fno-stack-protector

# Clang may incorrectly inline functions with stack protector enabled into
# __restore_processor_state(): https://llvm.org/pr47479
CFLAGS_REMOVE_cpu.o := $(CC_FLAGS_LTO)

obj-$(CONFIG_PM_SLEEP)		+= cpu.o
obj-$(CONFIG_HIBERNATION)	+= hibernate_$(BITS).o hibernate_asm_$(BITS).o hibernate.o
