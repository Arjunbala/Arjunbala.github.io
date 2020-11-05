---
layout: page
title: Projects
---

## Research Projects

### Low Latency Scheduling for Serverless Platforms
The increased use of micro-services to build web applications has spurred the rapid growth of Function-as-a-Service (FaaS) or serverless computing platforms. While FaaS simplifies provisioning and scaling for application developers, it introduces new challenges in resource management that need to be handled by the cloud provider. Our analysis of popular serverless workloads indicates that schedulers need to handle functions that are very short-lived, have unpredictable arrival patterns, and require expensive setup of sandboxes. The challenge of running a large number of such functions in a multi-tenant cluster makes existing scheduling frameworks unsuitable.
We present Archipelago, a platform that enables low latency request execution in a multi-tenant serverless setting. Archipelago views each application as a DAG of functions, and every DAG in associated with a latency deadline. Archipelago achieves its per-DAG request latency goals by: (1) partitioning a given cluster into a number of smaller worker pools, and associating each pool with a semi-global scheduler (SGS), (2) using a latency-aware scheduler within each SGS along with proactive sandbox allocation to reduce overheads, and (3) using a load balancing layer to route requests for different DAGs to the appropriate SGS, and automatically scale the number of SGSs per DAG. Our testbed results show that Archipelago meets the latency deadline for more than 99% of realistic application request workloads, and reduces tail latencies by up to 36X compared to state-of-the-art serverless platforms.

**Pre-Publication:** [arxiv](https://128.84.21.199/pdf/1911.09849.pdf)

**Code:** Please contact me for access.


### Fair GPU Cluster Scheduling for ML Training Jobs
Modern distributed machine learning (ML) training workloads benefit significantly from leveraging GPUs. However, significant contention ensues when multiple such workloads are run atop a shared cluster of GPUs. A key question is how to fairly apportion GPUs across workloads. We find that established cluster scheduling disciplines are a poor fit because of ML workloads' unique attributes: ML jobs have long-running tasks that need to be gang-scheduled, and their performance is sensitive to tasks' relative placement.
We propose Themis, a new scheduling framework for ML training workloads. It's GPU allocation policy enforces that ML workloads complete in a finish-time fair manner, a new notion we introduce. To capture placement sensitivity and ensure efficiency, Themis uses a two-level scheduling architecture where ML workloads bid on available resources that are offered in an auction run by a central arbiter. Our auction design allocates GPUs to winning bids by trading off efficiency for fairness in the short term but ensuring finish-time fairness in the long term. Our evaluation on a production trace shows that Themis can improve fairness by more than 2.25X and is ~5% to 250% more cluster efficient in comparison to state-of-the-art schedulers.

**Publication:** [NSDI 2020](https://www.usenix.org/system/files/nsdi20-paper-mahajan.pdf)

**Code:** Please contact me for access.


### Accelerating Deep Learning Inference via Freezing
Over the last few years, Deep Neural Networks (DNNs) have become ubiquitous owing to their high accuracy on real-world tasks. However, this increase in accuracy comes at the cost of computationally expensive models leading to higher prediction latencies. Prior efforts to reduce this latency such as quantization, model distillation, and any-time prediction models typically trade-off accuracy for performance. In this work, we observe that caching intermediate layer outputs can help us avoid running all the layers of a DNN for a sizeable fraction of inference requests. We find that this can potentially reduce the number of effective layers by half for 91.58% of CIFAR-10 requests run on ResNet-18. We present Freeze Inference, a system that introduces approximate caching at each intermediate layer and we discuss techniques to reduce the cache size and improve the cache hit rate. Finally, we discuss some of the open research challenges in realizing such a design.

**Paper:** [Freeze Inference](freeze_inference.pdf)

**Publication:** [HotCloud'19](https://www.usenix.org/conference/hotcloud19/presentation/kumar)

**Code:** Please contact me for access.

----

## Graduate Course Projects

#### Scheduling for HTAP systems on CPU-GPU clusters
HTAP systems that run a combination of OLAP and OLTP queries can be built to leverage the advantages offered bythe next generation hardware such as GPUs and accelerators. GPUs have abundant parallelism and high memory bandwidth, and thus there has been considerable interest in utilizing GPUs to accelerate OLAP workloads. In this work, we explore the idea of how a cluster of CPU-GPU co-processor servers can be used to accelerate HTAP workloads. We tackle the interesting problem of scheduling this mixture of queries across a heterogeous cluster by focusing on efficient query routing, and GPU memory management. We propose EEVEE, a heuristic-based scheduler for HTAP systems that performs intelligent scheduling decisions to improve overall latency and throughput of query execution. We implemented a simulator to evaluate the performance of executing HTAP queries on a cluster of CPUs and GPUs. We evaluate our design on a series of micro-benchmarks and SSB workloads and obtain gains of up to 6X by using a heterogeous cluster, and our heuristic scheduling policy results in 4X improvement in the makespan compared to our baseline policy.

**Paper:** [HTAP Scheduling](wisc-cs839-ngdb20-paper177.pdf)

**Code:** [Github](https://github.com/Arjunbala/HTAP-Scheduling)

### FAST PS: A Fast Publish-Subscribe service using RDMA
We present FAST PS, a fast publish-subscribe service that utilizes RDMA both for fast transport and for efficient CPU offload. We first present requirements from a new class of applications that have very different requirements from the use-case for which Queue Management Systems were designed for. These requirements motivate a ground-up redesign of such systems with RDMA at the heart of it.

**Paper:** [FASTPS Proposal](FastPS_Report.pdf)

**Code:** [Github](https://github.com/Arjunbala/RDMAPubSub/)


### Unwritten Contract for Distributed Systems on SSDs
The distributed systems of today are designed using the guidance of the CAP theorem. Distributed systems need to be able to tolerate network partition and hence the CAP theorem boils down to a trade-off between consistency and availability. In this work, we show that the CAP Theorem is no longer self-sufficient to serve as the holy grail for distributed system design in wake of modern storage media such as SSDs. Due to their unique wearing characteristics, it is essential to be able to reason about SSD cluster lifetime while designing distributed systems. In this work, we propose a new CLAP Theorem to encapsulate lifetime within the CAP theorem. Throughcarefully crafted simulation experiments over a variety of modern workloads, we showcase how different strategies for consistency can have huge effects on the lifetime of the SSD cluster.

**Paper:** [Unwritten Contract for Distributed Systems on SSDs](Unwritten_Contract_Distributed.pdf)

**Code:** [Github](https://github.com/Arjunbala/DistributedSystemsSSDs)


### SS-KVSTORE: Simple and Small Key-Value Store
This study presents our experiences in designing and implementing a simple and small key-value store named SS-KVSTORE . We first outline the mechanism for building a key-value store assuming that there are no failures and then outline how failure handling can be incorporated into our mechanisms. We find that we can implement a highly reliable and performant key-value store by using just a small amount of auxiliary metadata associated with each key-value pair. Evaluation on a prototype implementation shows that SS-KVSTORE is able to achieve a read throughput of up to ~1400 keys/sec and a write throughput of up to ~45 keys/sec.

**Paper:** [SS-KVSTORE](SS_KVStore.pdf)

**Code:** [Github](https://github.com/Arjunbala/KVStore)


### Advanced Operating Systems Mini Project
This work presents an insight into how subtle intricacies between system calls in UNIX-based systems play an
important role in the performance of an application. We compare two sets of aspects - (I) Buffered I/O vs Direct I/O
(II) Mutexes vs Spin-locks. Through carefully crafted workloads that emulate actual applications, we compare the
performance of these OS techniques. Our experiments show huge differences in performance depending on the kind
of workload. As a contribution, we provide a set of learnings to developers on the appropriate use of these seemingly
similar OS techniques.

**Paper:** [Advanced OS Mini Project](Advanced_OS_MiniProject.pdf)

**Code:** [Github](https://github.com/Arjunbala/Advanced-OS-MiniProject)


### Data Science Course Project
The goal of this project is to get our hands "dirty" as a budding data scientist (and to practice certain materials taught in the class). The project helped us gain a much better appreciation for working with "data in the wild", a better understanding of what it means to work as a data scientist, a deeper understanding of the class materials, a deeper understanding of how to use and debug machine learning models, a chance to work with popular data science tools in Python, and a glimpse into some research efforts in data science.

Specifically, in this project, we collected data, "wrangled" the data by extracting/cleaning/matching/integrating the data into a single unified data set, then analyzed that data set to infer insights.

**Website:** [Project Webpage](https://rohit--sharma.github.io/CS839_DataScience/)


### Big Data Systems Course Assignments
Course assignments for Big Data Systems had us playing around with Apache Spark and TensorFlow.

**Code and Reports:** [Big Data Assignments](https://github.com/Arjunbala/CS744-Assignments)


### Artificial Intelligence Course Assignments
**Code:** [AI Assignments](https://github.com/Arjunbala/CS540-Intro-to-AI)
