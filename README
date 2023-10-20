### Project Setup

#### Assignment 1

1. **VMWare Workstation Setup**
   - Download and install VMware Workstation.

2. **Create a Virtual Machine**
   - Download the Ubuntu ISO.
   - Create a Virtual Machine in VMware Workstation for Ubuntu.

3. **Enable Nested Virtualization**
   - In the VM settings, select nested virtualization capabilities.

4. **Fork the Linux Repository**
   - Fork the original Linux repository from Linus Torvalds' GitHub.

5. **Check VM's Virtualization Capabilities**
   - Inside the VM, check virtualization capabilities using the command `cat /proc/cpuinfo`.

6. **Install Git**
   - Install Git on the VM using the command `sudo apt-get install git`.

7. **Clone the Forked Repository**
   - Clone the forked Linux repository from your GitHub account.

8. **Edit Source Code**
   - Navigate to the cloned repository using `cd linux`.
   - In `cmpe283-1.c`, add sections of code for primary procbased controls, secondary procbased controls, entry, and exit controls based on the SDM.

9. **Create a Folder for Your Module**
   - Create a folder named `cmpe283` and place the modified `cmpe283-1.c` file and the Makefile inside it.

10. **Kernel Building and Installation**
    - Run the following commands in sequence:
      - `make menuconfig` (do not save any changes in the UI and exit)
      - `cp /boot/config-<current version>` (replace `<current version>` with the version from `uname -a`)
      - `make oldconfig` (press Enter to answer all questions)
      - `make prepare`
      - `make -j <number of cores>` (e.g., `make -j 4`)
      - If you encounter an error related to 'debian/canonical-certs.pem', edit the `.config` file and set the system trusted keys and revocation keys strings to empty.
      - `make -j <number of cores>` (e.g., `make -j 4`)
      - `sudo make INSTALL_MOD_STRIP=1 modules_install`
      - `sudo make install`
      - `sudo reboot`

11. **Check Kernel Version**
    - After the reboot, run `uname -a` to check that the kernel version has changed.

12. **Load and Test Your Module**
    - Change directory to the `cmpe283` folder.
    - Run `make` to compile your module.
    - After a successful compile, check that the `.ko` file is created using `lsmod | grep cmpe283`.
    - Insert your module with `sudo insmod cmpe283-1.ko`.

13. **View Module Information**
    - Run `dmesg` to view capability information for all the MSR defined in `cmpe283-1.c` under the heading "Module Start."

14. **Remove Your Module**
    - To remove the module, run `sudo rmmod cmpe283-1`.
    - Check the exit message with `dmesg` ("Module Exits").

#### Assignment 2

1. **Start with Assignment 1 Setup**

2. **Modify the cpuid.c and vmx.c Files**
   - Make the necessary modifications to the `cpuid.c` and `vmx.c` files based on the requirements for tracking exits.

3. **Compile and Install the Kernel**
   - Run the following commands:
     - `make -j 4 modules`
     - `make INSTALL_MOD_STRIP=1 modules_install && make install`

4. **Unload Existing KVM Modules**
   - Run `lsmod | grep kvm`.
   - If modules are loaded, run `rmmod kvm` and `rmmod kvm_intel`.

5. **Load KVM Module**
   - Run `modprobe kvm`.

6. **Install Virtual Machine Manager**
   - Install Virtual Machine Manager from the Ubuntu Software Center.

7. **Create an Inner VM**
   - Download an Ubuntu ISO and install an Ubuntu VM inside your existing VM (inner VM).

8. **Install cpuid Package**
   - Inside the inner VM, install the `cpuid` package using `sudo apt-get install cpuid`.

9. **Test Modifications**
   - Use the `cpuid` commands to observe the total exits and exit reasons as described in Assignment 2.

#### Assignment 3

1. **Start with Assignment 2 Setup**

2. **Modify Kernel Code**
   - Make edits to `linux/arch/x86/kvm/cpuid.c` and `linux/arch/x86/kvm/vmx/vmx.c` to add CPUID leaf nodes for reporting exit times.

3. **Compile and Install the Kernel**
   - Follow the steps to compile and install the modified kernel as described in Assignment 2.

4. **Test Modifications**
   - Inside the inner VM, use the new CPUID leaf nodes to report exit times.

#### Assignment 4

1. **Start with Assignment 3 Setup**

2. **Run dmesg to Print Exit Counts**
   - Run `dmesg` to print counts for exit reasons.

3. **Analyze Exit Counts**
   - Compare the exit counts between nested paging and shadow paging.

4. **Record Observations**
   - Record any changes in exit counts and reasons between the two paging methods.
