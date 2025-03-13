# Operating System

## Booting

> **Boot Process**
> Turning on the computer is called Boot Process.

When we turn on the power button to GUI being display on the screen a lot of complex things will happen in between.

The boot process in latest system takes less time.

The complex things that happen during the boot process can be divided into five steps. They are

1. Power On

- When we switch on the power button the power will be supplied to the power supply component.
- It is responsible for supplying the power to all the hardware components like CPU, GPU, memory, storage, disk, external devices.

2. CPU loads the BIOS or UEFI

   BIOS - Basic Input Output System
   UEFI - Unified Extensible Firmware Interface

- CPU will also get the power supply. CPU is the main compnent responsible for turning on the computer.

- CPU loads the BIOS or UEFI programs from BIOS chip which is non-voltaile.

- BIOS programs are used in the older system and UEFI programs are used in the latest system. UEFI is used to manage the systems that are interconnected through the LAN.

- UEFI is advanced version of BIOS

- The BIOS or UEFI programs consists of instructions that initialize the system.

- Working:

  1.  CPU is initialized.
  2.  CPUS loads the BIOS or UEFI programs from BIOS chip.

3. BIOS or UEFI programs runs the tests and initialize the hardware

- BIOS or UEFI program loads the settings from the memory area which is backed up by the CMOS battery(Complementary Metal Oxide SemiConductor).
- The CMOS batter is very important part of CPu and system because it always keeps running through we power off the system. The memory area contains low level storage settings, clock.

- BIOS or UEFI program loads the settings and perform the POST(Power On Self Test). Every hardware has some test cases written. The hardware is tested against the test cases. If the hardware will pass the boot process move forward if it fails an error message will be displayed.

- POST initializes the hardware.

4. BIOS, UEFI programs hand over the booting process to Booting devices.

- The various booting devices are USB, disk, CD. Boot devices consists of boot loader which contains the instructions that actually turn on the operating system.

- In the systems that use BIOS, the boot loader is present at MBR(Master Boot Record). MBR is present at 0th index of the disk.

- In the systems that use the UEFI, the boot loader is present at EFI(Extensible Firmware Interface). EFR is present at separate partition inside the disk.

5. Boot loader loads the full operating system

- Boot loader is a program that fully loads the operating system.

- Boot loader program is different in different operating systems. They are

  - In windows - bootmgr.exe
  - In Linux - GRUB
  - In MAC - boot.efi

- The first four steps are same in all the operating systems. In the fifth step, based on the type of operating system used the boot loader program will vary.
