zephyr_sources(
	thread.c
	thread_entry_wrapper.S
	cpu_idle.S
	fast_irq.S
	fatal.c
	fault.c
	fault_s.S
	irq_manage.c
	cache.c
	timestamp.c
	isr_wrapper.S
	regular_irq.S
	swap.S
	sys_fatal_error_handler.c
	prep_c.c
	reset.S
	vector_table.c
	)

zephyr_sources_if_kconfig(irq_offload.c)
zephyr_sources_ifdef(CONFIG_ATOMIC_OPERATIONS_CUSTOM atomic.c)
add_subdirectory_ifdef(CONFIG_CPU_HAS_MPU mpu)
