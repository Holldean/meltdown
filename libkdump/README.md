#include "libkdump.h"

int main() {
	// initialize libkdump
	if(libkdump_init(libkdump_auto_config) != 0) {
		return -1;
	}
	
	size_t addr = 0xfffffffc00022a0ull;
	// use libkdump...
	int value = libkdump_read(addr);
	// output result
	printf("%c\n", value);
	
	// done, cleanup everything
	if(libkdump_cleanup() != 0) {
		return -1;
	}
	return 0;
}
