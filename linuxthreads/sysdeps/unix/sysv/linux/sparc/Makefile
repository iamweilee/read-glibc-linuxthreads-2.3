ifeq ($(subdir),linuxthreads)
# gcc has /usr/lib{,64}/crti.o hardcoded in the specs file, because otherwise
# it would normally find {64,32}bit crt[in].o.
LDFLAGS-pthread.so += -specs=$(objpfx)specs
before-compile += $(objpfx)specs
generated += specs
$(objpfx)specs:
	$(CC) $(CFLAGS) $(CPPFLAGS) -dumpspecs \
	  | sed 's,/usr/lib\(\|64\)/\(crt[in]\.o\),\2,g' > $@
endif
