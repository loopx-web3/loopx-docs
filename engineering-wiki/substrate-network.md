---
description: The substrate network is a peer-to-peer overlay infrastructure.
---

# 🏛 Substrate Network

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption><p>Self-organizing and autonomous overlay network.</p></figcaption></figure>

## P2P Overlay

The network overlay of LoopX AI network is a P2P substrate. Validators as peers communication and connect with each other through gossip protocols. The network is resilient to:

* jumpstart new validator joins by connecting them to an initial set of neighbors,
* handle validator departures as validators maintain a minimum number of neighbors, and
* formulate a random graph in which validators are randomly connected with each other.

Optimization techniques such as capacity aware routing and resource allocation are adopted to improve the network throughputs.

## Buffer Maps

Large models are divided into smaller size chunks for distributed model serving. Each validator may contain partial chunk set of various models. When validators are interested in serving a full model for network rewards, it propagates model fetching requests with the specific model id and chunk id. It may fetch the specific model chunks directly if the requested ones are available in neighboring validators as found in buffer maps. Otherwise, the requests will be further forwarded across the network.

## Distributed Hash Table

Distributed hash tables (DHTs) are used for chunk, validator and model indexing. Keys are available to fetch any data stored across the P2P overlays. It is a hash map data structure stored in the distributed systems formed by validators and other network participants. Key–value pairs are stored in a DHT and such a look-up service offers O(log n) where n is the number of nodes in the network.

## AI Model Serving

TensorFlow serving is integrated on top of the overlay network for generic model serving. TensorFlow is widely adopted by the industry and thus provides user friendly model APIs for model builders, client consumers and DApps.
