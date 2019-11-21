# TPU

> Tensor Processing Unit
>
> - Tensor Processing Unit developed by Google. For other devices that provide tensor processing for artificial intelligence. 
>   - Which is an **AI Accelerator**
>     - GPU
>     - FPGAs
>     - **ASICs** (Application Specific Integrated Circuit) √

## Example 

In-Datacenter Performance Analyasis of a Tensor Processing Unit  https://arxiv.org/ftp/arxiv/papers/1704/1704.04760.pdf 



 与[图形处理器](https://zh.wikipedia.org/wiki/圖形處理器)（GPU）相比，TPU采用低精度（8位）计算，以降低每步操作使用的[晶体管](https://zh.wikipedia.org/wiki/晶体管)数量。降低精度对于深度学习的准确度影响很小，但却可以大幅降低功耗、加快运算速度。同时，TPU使用了[脉动阵列](https://zh.wikipedia.org/w/index.php?title=脉动阵列&action=edit&redlink=1)的设计，用来优化[矩阵乘法](https://zh.wikipedia.org/wiki/矩阵乘法)与[卷积](https://zh.wikipedia.org/wiki/卷积)运算，减少[I/O](https://zh.wikipedia.org/wiki/I/O)操作。此外，TPU还采用了更大的片上内存，以此减少对[DRAM](https://zh.wikipedia.org/wiki/DRAM)的访问，从而更大程度地提升性能 

## Evolution & Trend

### Evolution

#### **1st Generation TPU**

> May 2016
>
> Google I/O
>
> - Google I/O: An annual developer conference
>
>   [1\]()

- An 8-bit matrix multiplication engine,
- Driven with **CISC instruction**s 
- By the host processor across a **PCIe 3.0 bus**. 
- It is manufactured on a **28 nm process** with a die size ≤ 331 $mm^2$. 
- The clock speed is **700 MHz** 
- And it has a **thermal design power of 28–40 W**. 
- It has **28 MB of on chip memory**, and **4 MiB of 32-bit accumulators** taking the results of a **256×256 systolic array** of **8-bit multipliers**.
- Within the TPU package is **8 GiB of dual-channel 2133 MHz DDR3 SDRAM** offering **34 GB/s of bandwidth**.
- Instructions transfer data to or from the host, perform matrix multiplications or convolutions, and apply activation functions

> In-Datacenter Performance Analyasis of a Tensor Processing Unit  https://arxiv.org/ftp/arxiv/papers/1704/1704.04760.pdf 

#### **2nd Generation TPU**

> May 2017
>
> Google I/O
>
>  [[2nd Generation TPU]](https://en.wikipedia.org/wiki/Tensor_processing_unit#cite_note-TFP_v2-10)  Cloud TPU

##### Limition of 1st G TPU

- limited by [memory bandwidth](https://en.wikipedia.org/wiki/Memory_bandwidth), using 16 [GB](https://en.wikipedia.org/wiki/Gigabyte) of [High Bandwidth Memory](https://en.wikipedia.org/wiki/High_Bandwidth_Memory) 
- The first-generation TPUs were limited to **integers**

##### Advance of 2nd G TPU

**1. Performance**

- **Single Chip**

  In the second-generation design increased **bandwidth** to **600 GB/s** ,**performance** to **45 tera[FLOPS](https://en.wikipedia.org/wiki/FLOPS)**.[[9\]](https://en.wikipedia.org/wiki/Tensor_processing_unit#cite_note-TPU_memory-9) 

- **4-Chip Module**

  The **TPUs** are then arranged into **four-chip** modules with a performance of **180 teraFLOPS**. [[V1 and V2\]](https://en.wikipedia.org/wiki/Tensor_processing_unit#cite_note-TFP_v2-10) 

- **256-Chip Pods**

  Then **64** of these **modules** are **assembled** into **256-chip pods** with **11.5 petaFLOPS** of performance.

**2. Data Type**

- The second-generation TPUs can also **calculate in floating point**. 
- This makes the second-generation TPUs useful for both **training and inference** of machine learning models. 
- Google has stated these second-generation TPUs will be available on the [Google Compute Engine](https://en.wikipedia.org/wiki/Google_Compute_Engine) for use in **TensorFlow applications**

#### **3rd Generation TPU**

> May 8, 2018.
>
> Google I/O
>
> [3rd Generation]( https://www.top500.org/news/google-offers-glimpse-of-third-generation-tpu-processor/ )

- Google announced that processors themselves are **Twice as powerful as the second-generation TPUs**
- Would be **deployed in pod**s with **four times as many chips** as the preceding generation.[[13\]](https://en.wikipedia.org/wiki/Tensor_processing_unit#cite_note-13)[[14\]](https://en.wikipedia.org/wiki/Tensor_processing_unit#cite_note-14) 
- This results in an **8-fold increase** in **performance** **per pod** (with up to **1,024 chips per** pod) compared to the second-generation TPU deployment. 

**Edge TPU**

> In July 2018, Google announced the Edge TPU. 

- The Edge TPU is Google’s purpose-built [ASIC](https://en.wikipedia.org/wiki/Application-specific_integrated_circuit) chip designed to run machine learning (ML) models for [edge computing](https://en.wikipedia.org/wiki/Edge_computing)

- Meaning it is **much smaller** and **consumes far less power** compared to the TPUs hosted in Google datacenters (also known as [Cloud TPUs](https://cloud.google.com/tpu/)). 

> In January 2019

- Google made the Edge TPU available to developers with a line of products under the **[Coral](https://coral.withgoogle.com/) brand**.

- The product offerings include a [single board computer](https://en.wikipedia.org/wiki/Single_board_computer) (SBC)
- A [system on module](https://en.wikipedia.org/wiki/System_on_module) (SoM), a [USB](https://en.wikipedia.org/wiki/USB) accessory
- A mini [PCI-e](https://en.wikipedia.org/wiki/PCI-e) card
- And an [M.2](https://en.wikipedia.org/wiki/M.2) card. 
- The [SBC](https://en.wikipedia.org/wiki/Single_Board_Computer) [Coral Dev Board](https://coral.withgoogle.com/products/dev-board) and [Coral SoM](https://coral.withgoogle.com/products/som) both run Mendel Linux OS – a derivative of [Debian](https://en.wikipedia.org/wiki/Debian). 
- The USB, PCI-e, and M.2 products function as **add-ons** to **existing computer systems**, and support **Debian-based Linux systems** on **x86-64 and ARM64 hosts** (including [Raspberry Pi](https://en.wikipedia.org/wiki/Raspberry_Pi)).

- The machine learning runtime used to execute models on the Edge TPU is based on [TensorFlow Lite](https://en.wikipedia.org/wiki/TensorFlow).[[15\]](https://en.wikipedia.org/wiki/Tensor_processing_unit#cite_note-15) 
- The Edge TPU is only capable of **accelerating forward-pass operations**, which means it's primarily useful for performing **inferences** (although it is possible to perform lightweight transfer learning on the Edge TPU[[16\]](https://en.wikipedia.org/wiki/Tensor_processing_unit#cite_note-16)). 
- The Edge TPU also only supports **8-bit math**, meaning that for a network to be compatible with the Edge TPU, it needs to be trained using **TensorFlow** [quantization-aware training](https://github.com/tensorflow/tensorflow/tree/r1.13/tensorflow/contrib/quantize) technique.

> On November 12, 2019

-  [Asus](https://en.wikipedia.org/wiki/Asus) announced a pair of [single-board computer (SBCs)](https://en.wikipedia.org/wiki/Single-board_computer) featuring the Edge TPU. 
- The [Asus Tinker Edge T and Tinker Edge R Board](https://en.wikipedia.org/wiki/Asus_Tinker_Board) designed for [IoT](https://en.wikipedia.org/wiki/Internet_of_things) and [edge](https://en.wikipedia.org/wiki/Edge_computing) [AI](https://en.wikipedia.org/wiki/AI). 
- The SBCs support [Android](https://en.wikipedia.org/wiki/Android_(operating_system)) and [Debian](https://en.wikipedia.org/wiki/Debian) [operating systems](https://en.wikipedia.org/wiki/Operating_system).[[17\]](https://en.wikipedia.org/wiki/Tensor_processing_unit#cite_note-17)[[18\]](https://en.wikipedia.org/wiki/Tensor_processing_unit#cite_note-18) 
- ASUS has also demoed a **mini PC** called **Asus PN60T** featuring the Edge TPU.

### Trend 

> https://www.zhihu.com/question/46692744 

**TPU和GPU不是谁取代谁的问题**（敲黑板！）而是各自都有生存的空间，谁也不能取代谁。比一比性能只是互相学习和参照罢了。 

#### 1. 性能 Performance

**性能**是说 Performance 和 Performance/Watt

- **只比较性能（Tera Operations / Sec）是不全面的！只比较 Performance / Watt 也是不对的！**刚才说了。不能单纯做除法，50 Watt，5Watt，3Watt，都是云端/嵌入式终端的硬性限制。满足这个限制基础上，再来谈 Performance / Watt 才有意义。

#### 2. 功能 Function

**功能**是说 Training 和 Inference

#### 3. 性价比 Cost performance

|       | GPU  | TPU   |
| ----- | ---- | ----- |
| Price | 200$ | 1000$ |
|       |      |       |
|       |      |       |

#### 4. Motivations

>  **TPU不是终点，而只是开始。**

**Neural network algorithm** 

神经网络算法一直在演变和发展，这套方法的理论还不成熟

##### Application Secenarios (Market)

- Embeded 
- Robotic

应用场景也会在未来几年发生巨大的变化。大家可以想象一下安防、无人机、智慧大楼、无人驾驶，等等等等。每一个子领域都有 **系统/功耗/性能** 一系列问题和各种权衡。一方面，是算法多变的情况下

##### Direction

- **高效编程接口**

  *如何发掘计算的内在并行性，又给上层程序员提供一个高效的编程接口，是一个很重要很实际的问题。*

- **定制化**

  *另一方面，也有可能会做得极其定制化。牺牲大量编程性以求极低的功耗和性能，比如手机上专门做一个只识别人脸的芯片*