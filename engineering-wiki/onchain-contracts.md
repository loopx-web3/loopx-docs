---
description: >-
  Contracts are the onchain interfaces to publish and consume LoopX AI
  predictions.
---

# 🌈 Onchain Contracts

<figure><img src="../.gitbook/assets/contracts-loopx (1).svg" alt=""><figcaption><p>Contracts are called by DApps for onchain applications and consumer SDKs for offchain applications. It is the interface with offchain and onchain services.</p></figcaption></figure>

In the following, we use EVM contract code as an illustration of the onchain contract design. Contracts on other chains are designed similarly.

## Contract Interfaces

```
// AI prediction getter
function getPredictionFeed(
    string memory entityAddress
) external view returns (LoopXStructs.PredictionFeed memory predictionFeed);

// AI prediction putter
function updatePredictionFeeds(
    bytes[] calldata updateData
) external payable;
```

## Data Abstractions

```
// A prediction is scores and tags associated with an entity.
struct Prediction {
    string[] tags;
    // Unix timestamp describing when the prediction was published
    uint64 publishTime;
    int64 reputationScore;
}

// A model is a generic model data structure.
struct Model {
    // unique identifier for this model type
    uint8 modelID;
    // model description
    string modelName;
}

// An entity is blockchain wallet, token or protocol.
enum Entity {
    WALLET,
    TOKEN,
    PROTOCOL
}

// PredictionFeed represents a specific entity's prediction.
struct PredictionFeed {
    // The entity address.
    string entityAddress;
    Entity entity;
    Prediction prediction;
    Model model;
}
```

## Onchain Logging

Events are used for logging on EVM chains.

```
/// @title ILoopXEvents contains the events that LoopX contract emits.
/// @dev This interface can be used for listening to the updates for off-chain and testing purposes.
interface ILoopXEvents {
    /// @dev Emitted when the prediction feed with `entityAddress` has received a fresh update.
    /// @param entityAddress The LoopX Prediction Feed EntityAddress.
    /// @param entityType Entity Type of the given EntityAddress, 0, 1, 2...
    /// @param publishTime Publish time of the given price update.
    event PredictionFeedUpdate(
        string indexed entityAddress,
        uint8 entityType,
        uint64 publishTime,
        string[] tags,
        int64 reputationScore,
        uint8 modelID,
        string modelName
    );

    event BatchPredictionFeedUpdate(uint16 chainId, uint64 sequenceNumber);
}
```
