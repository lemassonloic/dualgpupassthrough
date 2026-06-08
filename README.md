
Dual GPU Passthrough — Proxmox VE

Two independent Windows workstations on a single physical machine using KVM, VFIO and IOMMU.

Project overview
This project transforms a single physical machine into two fully independent and simultaneous Windows workstations, each with its own dedicated GPU, isolated network interface and dedicated peripherals.
No shared resources between the two environments. No intermediate graphical virtualization. Native-level performance on both.
Technical stack

Hypervisor : Proxmox VE 8 (KVM / QEMU)
GPU passthrough : VFIO / IOMMU / PCIe passthrough
Host CPU : AMD Ryzen 9 5900X (12c / 24t)
GPU A : NVIDIA RTX 4060 → VM A (Windows)
GPU B : AMD RX 5500 XT → VM B (Windows)
RAM : 32 GB DDR4 3200 MHz
Network : 3 separate physical interfaces (management + VM A + VM B)
Storage : NVMe SSD (Proxmox OS) + 2x SATA SSD (VMs)

What was solved

Loss of Proxmox web access when both VMs started simultaneously → resolved by dedicated network interface architecture
Black screen on VM startup → resolved via video=efifb:off kernel parameter
GPU not detected by guest OS → resolved via VFIO binding and native driver blacklisting
PCIe isolation issues on A520 chipset → resolved by verifying and working around IOMMU group limitations

Documentation
📄 The full technical documentation (26 pages) is available here :

[LOÏC LEMASSON DUAL GPU PASSTHROUGH.pdf](https://github.com/user-attachments/files/28704569/LOIC.LEMASSON.DUAL.GPU.PASSTHROUGH.pdf)
Author
Loïc Lemasson — Self-taught system engineer — Saint-Lô, Normandie, France
📩 lemasson.loic50@gmail.com
🔗 LinkedIn : https://www.linkedin.com/in/lo%C3%AFc-lemasson-624896413/
