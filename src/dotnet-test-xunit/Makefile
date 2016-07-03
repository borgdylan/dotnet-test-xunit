PATH := $(shell pwd)/build:$(PATH)
prefix:= /usr/local

all:
	-dotnet restore
	-dotnet -v publish --configuration release_x86 -f net451 --output build

install:
	mkdir -p $(prefix)/lib/dotnet-test-xunit
	cp build/*.dll $(prefix)/lib/dotnet-test-xunit
	cp build/*.exe $(prefix)/lib/dotnet-test-xunit
	cp dotnet-test-xunit $(prefix)/lib/dotnet-test-xunit
	chmod a+x $(prefix)/lib/dotnet-test-xunit
	ln -sf $(prefix)/lib/dotnet-test-xunit/dotnet-test-xunit $(prefix)/bin/dotnet-test-xunit
	
uninstall:
	rm $(prefix)/bin/dotnet-test-xunit
	rm -r $(prefix)/lib/dotnet-test-xunit

.PHONY: all install uninstall
