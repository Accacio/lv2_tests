
all: amp.lv2/

amp.lv2/: amp.so amp.ttl manifest.ttl
	@echo Bundling ...
	@mkdir -p amp.lv2/
	@cp amp.so amp.ttl manifest.ttl amp.lv2/

amp.so: amp.c
	gcc -shared -O2  amp.c -o amp.so

clean:
	rm -rf amp.lv2 amp.so

install: amp.lv2/
	cp -r amp.lv2 ~/.lv2/

uninstall:
	rm -rf  ~/.lv2/amp.lv2

test:
	jalv.gtk3 http://accacio_amp
