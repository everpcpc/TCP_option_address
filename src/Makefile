#
# Makefile for the IPVS TOA  modules on top of IPv4 & IPv6.
#

obj-$(CONFIG_TOA) += toa.o

default:
	make CONFIG_TOA=m  -C /lib/modules/`uname -r`/build M=`pwd` modules EXTRA_CFLAGS="-DTOA_IPV6_ENABLE"

debug:
	make CONFIG_TOA=m  -C /lib/modules/`uname -r`/build M=`pwd` modules EXTRA_CFLAGS="-DTOA_IPV6_ENABLE -DTOA_DEBUG_ENABLE"
clean:
	rm -f .*.cmd *.o *.o.d *.ko *.mod.c *.mod modules.order Module.symvers
	rm -rf .tmp_versions
install:
	test -d "$(DESTDIR)/lib/modules/`uname -r`/extra/net/toa" \
		|| mkdir -p "$(DESTDIR)/lib/modules/`uname -r`/extra/net/toa"
	cp *.ko  "$(DESTDIR)/lib/modules/`uname -r`/extra/net/toa"
