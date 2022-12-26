ifndef ARCH
$(error $$ARCH not set)
endif

#
# This is just a build hack at this point.
#
all:
	sudo dpkg -i $(X1)/REPO/$(ONL_DEBIAN_SUITE)/packages/binary-$(ARCH)/libsaibcm_*.deb
	sudo dpkg -i $(X1)/REPO/$(ONL_DEBIAN_SUITE)/packages/binary-$(ARCH)/libsaibcm-dev_*.deb
	$(CROSS_COMPILER)gcc -o sai-sanity \
	-Wl,--rpath=/home/wsvm/skulambi/gs/2412/goldstone-buildimage/temp/lib64 \
	-Wl,--dynamic-linker=/home/wsvm/skulambi/gs/2412/goldstone-buildimage/temp/lib64/ld-linux-x86-64.so.2 \
	-g $(X1)/packages/base/any/sai-sanity/sai-sanity.c -I/usr/include/sai -lsai
