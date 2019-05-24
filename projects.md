---
layout: page
title: Projects
---

## Accelerating Deep Learning Inference via Freezing
Over the last few years, Deep Neural Networks (DNNs) have become ubiquitous owing to their high accuracy on real-world tasks. However, this increase in accuracy comes at the cost of computationally expensive models leading to higher prediction latencies. Prior efforts to reduce this latency such as quantization, model distillation, and any-time prediction models typically trade-off accuracy for performance. In this work, we observe that caching intermediate layer outputs can help us avoid running all the layers of a DNN for a sizeable fraction of inference requests. We find that this can potentially reduce the number of effective layers by half for 91.58% of CIFAR-10 requests run on ResNet-18. We present Freeze Inference, a system that introduces approximate caching at each intermediate layer and we discuss techniques to reduce the cache size and improve the cache hit rate. Finally, we discuss some of the open research challenges in realizing such a design.

**Paper:** [Freeze Inference] {freeze_inference.pdf}
**Publication:** [HotCloud'19] {https://www.usenix.org/conference/hotcloud19/presentation/kumar}
**Code:** Please contact me for access to code
