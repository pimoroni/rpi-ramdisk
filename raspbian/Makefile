all: initrd

initrd: multistrap.conf excludes.conf build ../kernel/kernel-root.tar.gz ../kernel/kernel7-root.tar.gz ../packages/pymtpd/pymtpd.tar.gz
	./build

clean:
	rm -rf root/ initrd

.PHONY: clean
