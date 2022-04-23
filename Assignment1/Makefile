obj-m += 1-cmpe283.o
all:
	make -C /lib/modules/$(shell uname -r)/build M=$(PWD) modules
clean:
	make -C /lib/modules/$(shell yname -r)/build M=$(PWD) clean
