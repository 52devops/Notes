Xen与KVM的不同
内存上Xen会开启自己的一套进程，与原有操作系统的内存管理应用同时工作在底层  
KVM有利用内核特性，使用原有的内存管理系统来管理物理内存。做功更少。借用用户空间的进程来交互  