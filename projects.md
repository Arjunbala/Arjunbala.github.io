---
layout: page
title: Projects
---

# Research Projects

## Accelerating Deep Learning Inference via Freezing
Over the last few years, Deep Neural Networks (DNNs) have become ubiquitous owing to their high accuracy on real-world tasks. However, this increase in accuracy comes at the cost of computationally expensive models leading to higher prediction latencies. Prior efforts to reduce this latency such as quantization, model distillation, and any-time prediction models typically trade-off accuracy for performance. In this work, we observe that caching intermediate layer outputs can help us avoid running all the layers of a DNN for a sizeable fraction of inference requests. We find that this can potentially reduce the number of effective layers by half for 91.58% of CIFAR-10 requests run on ResNet-18. We present Freeze Inference, a system that introduces approximate caching at each intermediate layer and we discuss techniques to reduce the cache size and improve the cache hit rate. Finally, we discuss some of the open research challenges in realizing such a design.

**Paper:** [Freeze Inference](freeze_inference.pdf)

**Publication:** [HotCloud'19](https://www.usenix.org/conference/hotcloud19/presentation/kumar)

**Code:** Please contact me for access.


## Unwritten Contract for Distributed Systems on SSDs
The distributed systems of today are designed using the guidance of the CAP theorem. Distributed systems need to be able to tolerate network partition and hence the CAP theorem boils down to a trade-off between consistency and availability. In this work, we show that the CAP Theorem is no longer self-sufficient to serve as the holy grail for distributed system design in wake of modern storage media such as SSDs. Due to their unique wearing characteristics, it is essential to be able to reason about SSD cluster lifetime while designing distributed systems. In this work, we propose a new CLAP Theorem to encapsulate lifetime within the CAP theorem. Throughcarefully crafted simulation experiments over a variety of modern workloads, we showcase how different strategies for consistency can have huge effects on the lifetime of the SSD cluster.

**Paper:** [Unwritten Contract for Distributed Systems on SSDs](Unwritten_Contract_Distributed.pdf)

**Code:** [Github](https://github.com/Arjunbala/DistributedSystemsSSDs)


## Fair GPU Cluster Scheduling for ML Training Jobs
Modern distributed machine learning (ML) training workloads benefit significantly from leveraging GPUs. However, significant contention ensues when multiple such workloads are run atop a shared cluster of GPUs. ML training jobs have unique characteristics - they are typically long-running, sensitive to placement of workers across GPUs in the cluster, and often consist of multiple hyper-parameter explorations. We seek to answer a key question - how to fairly apportion GPUs across ML jobs having these characteristics while maximizing cluster efficiency.

**Paper:** Please contact me for access.

**Code:** Please contact me for access.


## Low Latency Scheduling for Serverless Platforms
In this project, we look at how to minimize scheduling latencies in serverless computing.
Please contact me for more details.


# Graduate Course Projects

## Advanced Operating Systems Mini Project
This work presents an insight into how subtle intricacies between system calls in UNIX-based systems play an
important role in the performance of an application. We compare two sets of aspects - (I) Buffered I/O vs Direct I/O
(II) Mutexes vs Spin-locks. Through carefully crafted workloads that emulate actual applications, we compare the
performance of these OS techniques. Our experiments show huge differences in performance depending on the kind
of workload. As a contribution, we provide a set of learnings to developers on the appropriate use of these seemingly
similar OS techniques.

**Paper:** [Advanced OS Mini Project](Advanced_OS_MiniProject.pdf)
**Code:** [Github](https://github.com/Arjunbala/Advanced-OS-MiniProject)


## Data Science Course Project
The goal of this project is to get our hands "dirty" as a budding data scientist (and to practice certain materials taught in the class). The project helped us gain a much better appreciation for working with "data in the wild", a better understanding of what it means to work as a data scientist, a deeper understanding of the class materials, a deeper understanding of how to use and debug machine learning models, a chance to work with popular data science tools in Python, and a glimpse into some research efforts in data science.

Specifically, in this project, we collected data, "wrangled" the data by extracting/cleaning/matching/integrating the data into a single unified data set, then analyzed that data set to infer insights.

**Website:** [Project Webpage]https://rohit--sharma.github.io/CS839_DataScience/


## Big Data Systems Course Assignments
Course assignments for Big Data Systems had us playing around with Apache Spark and TensorFlow.
**Code and Reports:** [Big Data Assignments](https://github.com/Arjunbala/CS744-Assignments)


## Artificial Intelligence Course Assignments
**Code:** [AI Assignments](https://github.com/Arjunbala/CS540-Intro-to-AI)
