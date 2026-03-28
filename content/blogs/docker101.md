+++
title = "Docker 101: Stuff you need to know before diving into docker"
date = 2024-03-14T12:00:00+05:30
type = "post"
description = "Pre-requisite for learning docker"
in_search_index = true
[taxonomies]
tags = ["docker", "virtualization"]
[extra]

+++

![docker101](/images/blogs/docker101.png)

Before delving into Docker usage, it's essential to grasp the purpose and significance of its existence. This blog will explore the evolutionary journey of virtualisation and Docker, shedding light on why containerisation emerged and its role in addressing specific needs.


## Evolution of Virtualisation

lets time travel little back in time and understand how the deployment and operations process was back then, and how it evolved.

1. **Bare Metal (Traditional Approach):**
   This was the conventional method of deploying an application involves installing and configuring it directly on a physical server or virtual server. This approach typically requires managing dependencies, ensuring compatibility, and handling potential conflicts with other applications on the same server. It was a time-consuming process and also lead to issues such as dependency clashes or difficulty in scaling applications seamlessly. This approach resulted into various problems like:

   * Low utilisation efficiency: Limited number of application can be deployed on such servers, which kept the rest of the hardware ideal, resulting into wastage of hardware resources
   * High blast radius: Small change in one application may result into failure of all other application on same server.
   * Dependency conflicts: In this system since the hardware and OS were shared along all the application. so if one application required version 1 of certain development package and other application require version 2 of same development package this gave rise to dependency conflicts.
2. **Virtual Machines:**
   To overcome the flaws of the traditional approach of deploying application the another subsequent approach was introduced, It involved the use of virtual machines (VMs). Instead of installing directly on physical servers, virtualisation enables the creation of multiple isolated virtual environments on a single physical machine. Each VM operated independently, with its own operating system and application stack. This approach helped solve dependency issues, enhances scalability, and provided more efficient utilisation of hardware resources compared to the traditional deployment model.
   Virtual machine has hypervisor to solve the problem of utilisation efficiency. Hypervisors are crucial component in virtualisation technology. They facilitate the creation and management of various virtual machines (VMs) on a physical host machine.
   **There are two main types of hypervisors:**

   * Type 1 Hypervisors (Bare-Metal Hypervisors): These hypervisors run directly on the host's hardware to control the hardware and to manage guest operating systems. They don't require a host operating system and are considered more efficient. Examples include VMware ESXi, Microsoft Hyper-V (when installed on bare metal), and AWS Nitro Systems.
   * Type 2 Hypervisors (Hosted Hypervisors): These hypervisors run on top of a host operating system, much like other computer programs. They are often used for development and testing scenarios. Examples include VMware Workstation, Oracle VirtualBox, and Parallels.

   **Benefits of this approach includes:**

   * There were no dependency issue in this approach.
   * It improved the speed and time of deployment process.

   **But it still had certain underline flaw like:**

   * Own kernel in every virtual machine resulting into higher storage requirement.
   * It did improve the blast radius but it small blast radius still existed in this system.
3. **Containerisation :**
   To further optimise the deployment process and to overcome the limitation and flows of virtual machine the containerisation approach was introduced. The containerisation approach for deploying applications involves encapsulating an application and its dependencies into a lightweight, portable unit known as a container. Containers provide a consistent and isolated environment for applications to run, irrespective of the underlying infrastructure. The key components of this approach include:

   1. **Containerisation Technology:** Docker is one of the most popular containerisation platforms. Containers package an application and its dependencies, libraries, and runtime into a single container image. This image is portable and can be executed consistently across different environments.

   **Benefits of the container approach include:**

   * Consistency: Containers ensure consistency across development, testing, and production environments, reducing the "it works on my machine" problem.
   * Isolation: Containers encapsulate applications, isolating them from the underlying system and other applications. This isolation improves security and avoids conflicts between dependencies.
   * Portability: Containerised applications can run on any system that supports the containerisation platform, whether it's on-premises, in the cloud, or on a developer's laptop.
   * Resource Efficiency: Containers share the host operating system's kernel, making them lightweight and efficient compared to traditional virtual machines.
   * Scalability: Containers can be quickly scaled up or down to accommodate varying workloads, providing flexibility and responsiveness.

   Overall, the container approach simplifies the deployment and management of applications, fostering agility, scalability, and efficiency in software development and operations.

## Conclusion

In conclusion, adopting the containerisation approach emerges as the preferred method for deploying and overseeing applications, effectively addressing key drawbacks associated with both bare metal and virtual machine approaches. This includes resolving dependency issues, mitigating the risk of a wide-ranging impact on applications (high blast radius), improving utilisation efficiency, and minimising/eliminating resource wastage.
