# Intro to AI Series: AI Accelerators


Scientific applications are increasingly adopting Artificial Intelligence (AI) techniques to advance science. There are specialized hardware accelerators designed and built to run AI applications efficiently. With a wide diversity in the hardware architectures and software stacks of these systems, it is challenging to understand the differences between these accelerators, their capabilities, programming approaches, and how they perform, particularly for scientific applications. 

We will cover an overview of the AI accelerators landscape with a focus on SambaNova, Cerebras, Graphcore, and Groq systems along with architectural features and details of their software stacks. We will have hands-on exercises that will help attendees understand how to program these systems by learning how to refactor codes written in standard AI framework implementations and compile and run the models on these systems. 



## Slides

* [Intro to AI Series: AI Accelerators]() 
    > Slides will be uploaded shortly after the talk.

## Hands-On Sessions


* [Cerebras](./Cerebras/README.md)
* [Graphcore](./Graphcore/README.md)  
* [SambaNova](./Sambanova/README.md)                                    
* [Groq](./Groq/README.md)        


### Director’s Discretionary Allocation Program

To gain access to AI Testbeds at ALCF after current allocation expires apply for [Director’s Discretionary Allocation Program](https://www.alcf.anl.gov/science/directors-discretionary-allocation-program)

The ALCF Director’s Discretionary program provides “start up” awards to researchers working to achieve computational readiness for for a major allocation award.

## Homework 

You need to submit either Theory Homework or Hands-on Homework. 

#####  Theory Homework
* What are the key architectural features that make these systems suitable for AI workloads?
* Identify the primary differences between these AI accelerator systems in terms of their architecture and programming models.
* Based on hands-on sessions, describe a typical workflow for refactoring an AI model to run on one of ALCF's AI testbeds (e.g., SambaNova or Cerebras). What tools or software stacks are typically used in this process?
* Give an example of a project that would benefit from AI accelerators and why?

## Solutions

1. What are the key architectural features that make these systems suitable for AI workloads?

I identified the architecture of AI accelerators having distinct characteristics that help them handle computationally intense workloads more efficiently:
* Data flows: Data flows through a network of processing elements, which is more efficient for parallel processing and high data throughput. 
* Spatially intelligent: Since memory is distributed across cores, this reduces the energy cost compared to traditional architecture. AI tasks that require low latency with high memory bandwidth benefit from the distributed structure like this. This also really speeds up the training process. 
* Reconfigurable: The SambaNova Reconfigurable Dataflow Unit (RDU) can be optimized for specific AI models by modifying execution paths. This is more efficient with better performance, such as for matrix multiplications and tensor operations.
Ultimately, these AI accelerators have hardware and on-chip memory specialized for memory intensive AI workloads.

2. Identify the primary differences between these AI accelerator systems in terms of their architecture and programming models.

| **Feature**             | **Cerebras CS-2**                                                                 | **SambaNova DataScale SN30**                                                                 | **Graphcore BowPod64**                                                                 | **Groq**                                                                 |
|-------------------------|-----------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
| **Architecture**        | Wafer-scale engine with 850,000 cores optimized for sparse linear algebra         | Tiled architecture with reconfigurable SIMD pipelines and distributed scratchpads            | Composed of Intelligence Processing Units (IPUs) with a bulk-synchronous parallel execution model                   | Large on-chip SRAM and a flat memory hierarchy; Tensor Streaming Processor (TSP)                           |
| **Programming Model**   | Dataflow programming where tasks are activated by data packets; highly parallel and scalable                    | Supports high-level ML graph transformation and optimizations using its graph compiler       | Utilizes the Poplar SDK for graph-based model execution; Bulk Synchronous Parallelism (BSP) for computation and communication in two phases                                | Utilizes the GroqFlow toolchain for seamless integration with PyTorch or TensorFlow models; deterministic execution for inference tasks |
| **Memory**              | 40GB on-chip SRAM with a high memory bandwidth of 20 PByte/s; processing elements (PEs) have their own memory and operate independently                     | 640 MB on-chip memory with extensive external memory support; terabytes of addressable memory with multi-tiered memory architecture                                | Features in-processor memory for each IPU to support high parallelism; interconnected processing tiles have their own core and local memory                   | Flat memory hierarchy exposed to software as directly addressable banks |


3. Based on hands-on sessions, describe a typical workflow for refactoring an AI model to run on one of ALCF's AI testbeds (e.g., SambaNova or Cerebras). What tools or software stacks are typically used in this process?

* Define a model with PyTorch or TensorFlow
* Integrate with Hardware API, like CerebrasAPI to map models to high-performance kernals
* Use a graph compiler, like Cerebras Graph Compiler to transform model into an optimized execution graph
* Deploy on hardware with runtime environments specific to your AI accelerator
* Use profiling tools to optimize compute and memory usage before execution, like the GroqView Profiler


4. Give an example of a project that would benefit from AI accelerators and why?

The 1000 Genomes project is one of the largest distributed data collection and analysis projects ever done in biology. Recent advances in genome-scale foundation models would significantly benefit from AI accelerators due to the intense computational power and memory bandwidth requires to churn through these datasets. For example, the wafer-scale architecture from Cerebras CS-2 would provide adequate resources to process these workloads in parallel, accelerating scientific discovery. 


##### Hands-on Homework

* [Cerebras Homework](./Cerebras/README.md#homework)
* [Sambanova Homework](./Sambanova/README.md#homework)
* [Graphcore Homework](./Graphcore/README.md#homework)
* [Groq Homework](./Groq/README.md#homework)

## Useful Links 

* [Overview of AI Testbeds at ALCF](https://www.alcf.anl.gov/alcf-ai-testbed)
* [ALCF AI Testbed Documentation](https://www.alcf.anl.gov/support/ai-testbed-userdocs/)
* [Director’s Discretionary Allocation Program](https://www.alcf.anl.gov/science/directors-discretionary-allocation-program)
* [ALCF Events Page](https://www.alcf.anl.gov/events/intro-ai-series-ai-accelerators-0)  

##### Acknowledgements

Contributors: [Siddhisanket (Sid) Raskar](https://sraskar.github.io/), [Murali Emani](https://memani1.github.io/), [Varuni Sastry](https://www.alcf.anl.gov/about/people/varuni-katti-sastry), [Bill Arnold](https://www.alcf.anl.gov/about/people/bill-arnold), and  [Venkat Vishwanath](https://www.alcf.anl.gov/about/people/venkatram-vishwanath).

> This research used resources of the Argonne Leadership Computing Facility, which is a DOE Office of Science User Facility supported under Contract DE-AC02-06CH11357.
