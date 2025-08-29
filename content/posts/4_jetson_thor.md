---
title: "NVIDIA's Jetson Thor Is Impressive"
date: 2025-08-28T00:12:09-05:00
draft: false 
tags: 
    - "artificial intelligence"
    - "robotics"
    - "hardware"
---
### Intro
NVIDIA recently released the Jetson Thor, their latest state-of-the-art chip in their Jetson line of products. 
It's impressive enough that it has awoken me from my slumber long enough to do a brief overview of its capabilities. 
Following the trend of its predecessors, Jetson Thor is marketed as an entire platform aimed at bringing interactive artificial intelligence into the physical plane. 

{{< figure 
    src="/thor.jpg" 
    alt="NVIDIA Jetson T5000 Module" 
    caption="NVIDIA Jetson T5000 Module" 
    attr="Image credit: NVIDIA" 
    attrlink="https://developer.nvidia.com/buy-jetson" 
>}}

### Hardware and Microarchitecture 

#### Blackwell GPU
The Jetson Thor T5000 features an NVIDIA Blackwell architecture GPU.
The [Blackwell architecture](https://images.nvidia.com/aem-dam/Solutions/geforce/blackwell/nvidia-rtx-blackwell-gpu-architecture.pdf) was announced in March 2024 and is used in their groundbreaking GB200 NVL72 data center chips and their more accessible RTX 50 series. 
It boasts CUDA cores with upgraded compute capability, new fifth-generation tensor cores, fourth-generation ray tracing cores, and introduces us to the AI Management Processor (AMP). 

The AMP is a RISC-V processor that implements a scheduling architecture to reduce the scheduling bottleneck between the CPU and the GPU. 
It's fashioned after Microsoft's Hardware-Accelerated GPU Scheduling (HAGS) to improve performance for games and AI-powered apps on Windows. 
I'm not super familiar with this particular processor and, at the moment, it's not entirely clear how it fits in with the rest of the Jetson Thor's functionalities.
The Blackwell documentation describes its purpose to enhance the scheduling of GPU contexts in Windows but most Jetson Nano chips run best with Ubuntu. 
I can't find any direct reference to the AMP in the actual Jetson webpages but I can only assume it is meant to enhance the video output experience in some way or speed up asynchronous AI model workloads on the edge.

These are important considerations and even non-technical folks might find it worthwhile to flip through the microarchitecture of these chips since it essentially determines a processor’s capabilities at the level right above the hardware itself. 
An impressive [SiFive processor](https://www.sifive.com/blog/introduction-to-sifive-vector-processors) with vector registers and vector ALUs is only fully useful when paired with the RISC-V ISA supporting the vector extension. 
Simply put, it's an important consideration when looking for a chip with competitive functionality and long-term support.

#### Everything Else
As for the rest of the Jetson Thor chip, we have an impressive multicore ARM Neoverse CPU, a line designed for HPC datacenters and edge computing. 
There's also dedicated hardware for high-quality video encoding and decoding, ideal for computer vision capabilities. 

The [Programmable Vision Accelerator v3 (PVA)](https://developer.nvidia.com/embedded/pva#section-how-it-works) is a programmable multi-core Digital Signal Processor (DSP) meant to offload certain computer vision tasks from the GPU.


The [Holoscan Sensor Bridge](https://docs.nvidia.com/holoscan/sensor-bridge/latest/introduction.html) is an FPGA chip that's not directly on chip but is worth noting as part of the Jetson Thor ecosystem. 
It implements sensor-over-Ethernet technology, enabling faster multi-sensor transportation of data to the GPU. 
As a result, robots using this chip will have sharper "reflexes" as they process input data faster.

{{< figure 
    src="/nvidia_sensor_bridge.jpeg" 
    alt="NVIDIA Sensor Bridge Architecture" 
    caption="NVIDIA Sensor Bridge Architecture" 
    attr="Image credit: NVIDIA" 
    attrlink="https://www.nvidia.com/en-us/technologies/holoscan-sensor-bridge/" 
>}}

More info on additional components such as USB ports, drive support, etc., for the Jetson Thor can be found [here](https://www.nvidia.com/en-us/autonomous-machines/embedded-systems/jetson-thor/).

### Software Tools and Ecosystem
The main draw of the Jetson line of products, in my opinion, is the advanced [software ecosystem](https://developer.nvidia.com/embedded/develop/software), designed to transfer and process data quickly. 

Along with the Jetpack SDK for developing on the Jetson platform, we also have the Holoscan SDK to directly work with the Holoscan Sensor Bridge. 
The [Holoscan SDK](https://docs.nvidia.com/holoscan/sdk-user-guide/index.html) pairs with the Holoscan Sensor Bridge by allowing developers to build directed graphs of "operators" to define data processing and ML workflows.
NVIDIA also gives us the [HoloHub](https://nvidia-holoscan.github.io/holohub/applications/), a repository of reference applications using the Holoscan SDK in a variety of fields.

[NVIDIA Metropolis](https://www.nvidia.com/en-us/autonomous-machines/intelligent-video-analytics-platform/) is NVIDIA's vision AI platform for the development and deployment of vision-based automations.
This platform provides the tools for advanced applications on both the edge and the cloud by combining sensor and visual data for model training and tuning.

Roboticists will likely appreciate the [NVIDIA Isaac Platform](https://developer.nvidia.com/isaac). Isaac provides its own [extension](https://developer.nvidia.com/isaac/ros) of ROS2 (Robot Operating System). 
On this foundation, Isaac also provides the [Isaac Manipulator](https://nvidia-isaac-ros.github.io/reference_workflows/isaac_manipulator/index.html) and the [Isaac Perceptor](https://developer.nvidia.com/isaac/perceptor). 
These are collections of CUDA-accelerated libraries and AI models that support applications for robotic manipulators and autonomous mobile robots respectively.

{{< figure 
    src="/nvidia_isaac.png" 
    alt="NVIDIA Isaac Platform and Workflows" 
    caption="NVIDIA Isaac Platform and Workflows" 
    attr="Image credit: NVIDIA" 
    attrlink="https://developer.nvidia.com/isaac" 
>}}

Isaac's final jewel is [Isaac GR00T](https://developer.nvidia.com/isaac/gr00t). 
GR00T refers to both the research initiative and the platform for developing foundational models for general purpose robots and humanoid robots. 
It provides foundation models such as the [N1](https://nvidianews.nvidia.com/news/nvidia-isaac-gr00t-n1-open-humanoid-robot-foundation-model-simulation-frameworks), a family of pretrained customizable models for general robotics applications.

GR00T also comes with data collection and generation workflows for collecting human demonstration data and generating [unique simulations for further training](https://www.youtube.com/watch?v=8Mwrfvq-GeY).

Jetson Thor can serve as the "brain" of Isaac-powered robots by utilizing all of the previously mentioned hardware and software for sensor data collection, data processing, and physical movement.
Investors and research companies like [Figure AI](https://blogs.nvidia.com/blog/figure-humanoid-robot-autonomous/) will find this extremely useful as they continue to plow ahead in the race for adaptive humanoid robots.

### "Competition" and Alternatives
"Competition" is in quotes here because it's hard to find an exact one-to-one competitor to NVIDIA on the hardware side of edge robotics. 
Some similar products to Blackwell's Tensor Cores include [Google's Edge TPU](https://coral.ai/products/) (Tensor Processing Unit). 
As the name indicates, the processor is optimized for matrix multiplication and tensor operations, both fundamental to any machine learning task. 
NVIDIA's GPU architecture around the Blackwell Tensor Cores provides more general-purpose functionality for robotics and multi-modal workloads.

There's also Tenstorrent with their RISC-V [Blackhole Tensix Processor](https://docs.tenstorrent.com/aibs/blackhole/) featuring "Tensix Cores" and their own software ecosystems. 
Their full line of products ranges from superscalar AI processors for datacenters to smaller chips meant to compete with GPUs for ML tasks. 
However, to my knowledge, their chips aren't marketed with a distinct focus on robotics. 
In addition to raw compute power, Jetson Thor goes to great lengths to provide multimedia sensor input processing capabilities and a vision accelerator, both crucial for physically interactive AI.

### Conclusion 
With the world's focus on enhanced gaming or AI automated workflows on our personal computers and servers, it might be hard to convince people to care about this member of the Blackwell family.
The way I see it, edge computing matters for businesses and individuals that enjoy the usefulness of AI but also value their privacy. 
The field of robotics matters since it takes the next step of bringing AI into the physical world.  
The Jetson Thor itself matters because it enables robotics development by providing a fully integrated ecosystem of sensors, a working ROS environment, and readily available multimodal AI models that can run on limited hardware. 
Speaking from experience, this is really not easy to set up on your own.

In summary, the Jetson Thor chip shows remarkable improvements in compute power, energy efficiency, and edge AI capabilities, proving that the age of general robotics is hardly a pipe dream. 