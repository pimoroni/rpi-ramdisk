include ../toolchain.mk

all: keybow.tar.gz

keybow.tar.gz: keybow.service init
	rm -rf --one-file-system $(STAGE)
	mkdir -p $(STAGE)
	cp init $(STAGE)/
	mkdir -p $(STAGE)/etc/systemd/system
	cp keybow.service $(STAGE)/etc/systemd/system/

	tar -C $(STAGE) -czf keybow.tar.gz .

install: keybow.tar.gz
	tar -xf keybow.tar.gz -C $(DESTDIR)
	$(MYCHROOT) $(DESTDIR) /bin/systemctl reenable keybow.service

clean:
	rm -rf --one-file-system $(STAGE) keybow.tar.gz

.PHONY: clean install
