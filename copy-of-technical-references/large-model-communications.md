---
description: Compressed learning is to reduce the large model by thousands of times.
---

# Large Model Communications

## The Large Model Challenge

A fundamental challenge of a decentralized learning framework is how to handle the huge communication cost caused by the large model size. This challenge will be solved efficiently via compressed training in our framework. Specifically, we will implement tensor-compressed training for efficient network communications, which has achieved the best compression so far in the training process.

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption><p>Reducing model parameters by compressing training variables via low-rank tensor factorization.</p></figcaption></figure>

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption><p>(a) A conventional decentralized learning method needs to share the full-size model information. (b) In our proposed tensor-compressed decentralized learning method, we only share the compressed tensor factors to save the communication cost.</p></figcaption></figure>

### Communication Cost Reduction

To address the communication bottleneck of decentralized learning, only θ needs to be transferred as shown above, so the latency caused by network communication can also be reduced significantly. Low-precision and mixed-precision representations can also be used to represent the compressed parameters, which can further reduce the communication cost. The key idea is to use a small number of binary bits to represent all variables in the tensor factors. Promising numerical results and hardware demo have been reported. Such low-precision representation will greatly save the computing, memory and communication cost in federated learning, but it will not cause significant loss of prediction accuracy due to the error-resilient nature of neural networks. The compressed model parameters can be stored on local devices with small memory cost to enable fast inference.
