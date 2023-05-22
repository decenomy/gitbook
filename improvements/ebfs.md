---
description: Enhanced Blockchain Features (EBFs)
---

# EBFs

### _<mark style="color:yellow;">EBF features are still in the work-in-progress phase</mark>_



Enhanced Blockchain Features (EBFs) refer to functional extensions of a regular UTXO-based blockchain, such as Bitcoin. Comparable to Ethereum contracts, EBFs are stateful and Turing complete, providing the ability to compose functionalities that complement and strengthen the regular stateless UTXO model. However, it is noteworthy that EBFs should not be authored or released by the general public since they will extend and interact with vital components of the blockchain. Such crucial components include the capacity for generating new coins, thereby rendering EBFs a high-security standard and sensitive element. EBFs amalgamate the practicability and determinism of a blockchain's UTXO model with the strengths of natively developed Turing complete functionalities.

### Structure

Enhanced Blockchain Features (EBF) infrastructure comprises multiple platforms, each designed to accommodate a set of interrelated additional functionalities. Each platform comprises contracts with various methods, each being assigned specific and unique tasks. It is critical to ensure that each method is fully deterministic and adheres to the principles of single responsibility and separation of concerns to enhance the efficiency and reliability of the EBF platform. By adhering to these principles, the EBF platform can offer a stable and dependable environment for executing contracts, thereby ensuring the security and stability of the blockchain ecosystem.

### Messaging

To invoke a contract method on an Enhanced Blockchain Features (EBF) platform, an EBF message must be issued. These messages are expressed as OP\_RETURN script transaction outputs on regular transactions. To distinguish them from regular OP\_RETURN scripts, EBF messages are identified by starting with an OP\_RETURN opcode and two checksum bytes.

Digital signatures are utilized to ensure the authenticity and integrity of EBF messages. The signatures are generated using the sender's private key, and executed against the entire transaction, thereby preventing a replay attack and preventing the need for a nonce field. In this manner, the EBF platform ensures that the same message cannot be used to modify the blockchain multiple times.

The following fields describe the EBF message generic envelope:

| Size | Name      | Type      | Description                                         |
| ---- | --------- | --------- | --------------------------------------------------- |
| 1    | op        | opcode    | OP\_RETURN `0x6A` opcode                            |
| 1+   | contract  | varint    | Contract id                                         |
| 1+   | method    | varint    | Method id                                           |
| 1+   | arguments | byte\[]   | Arguments                                           |
| 2    | checksum  | uint16\_t | First 2 bytes of sha256(sha256(contract-arguments)) |

### Message Processing

The processing of EBF messages involves several steps. First, the transaction containing the EBF message must be validated according to the blockchain rules. This includes checking that the inputs are valid and that the sender has the necessary funds to cover the transaction fees. Once the transaction is validated, the EBF message is extracted from the OP\_RETURN output script.

Next, the EBF message is deserialized, and the contract method specified in the message is located. The contract method is then executed, and any necessary state changes are made to the blockchain. This may involve modifying the balances of accounts or updating the state of smart contracts.

It is essential to note that EBF messages are executed deterministically, and any state changes must be consistent with the blockchain's current state. This ensures that the blockchain remains secure and that all nodes in the network can reach a consensus on the current state of the blockchain.

Due to blockchain technology's decentralized nature, blockchain network blocks may be subject to reorganization. Consequently, each contract method deployed on an Enhanced Blockchain Features (EBF) platform must have a robust process to handle reorganization events and restore the contract to its prior state in such an event. In the context of the EBF platform, a reorganization refers to a mechanism that restructures the blockchain network in response to a network-wide consensus failure, ensuring the integrity and consistency of the blockchain. The reorganization process is critical in enabling the EBF platform to maintain a reliable and secure environment for executing contracts, minimizing the risk of failure, data loss, inconsistency, or corruption during a blockchain reorganization.

In summary, the processing of EBF messages involves validating transactions, extracting and deserializing EBF messages, locating and executing contract methods, making necessary state changes to the blockchain, and preventing replay attacks through the use of transaction signatures.

### Block Processing

The validation of transactions constitutes a critical step in processing blocks within the EBF infrastructure. Upon adding a new block to the blockchain, it is imperative to ascertain the validity of the transactions contained within it and to ensure they conform to the regulations stipulated by the EBF platform. This validation procedure comprises a comprehensive review of the EBF messages and the digital signatures embedded within them, an examination of the transaction inputs and outputs, and a check to ensure the absence of double-spending and invalid EBF states. The nodes within the network undertake the validation process and participate in the consensus protocol, arriving at a collective agreement on the veracity of the transactions within the block. Upon successful validation, the transactions are appended to the block and propagated to the other nodes within the network. The block processing mechanism within the EBF infrastructure closely resembles that of the conventional blockchain, with the additional layer of EBF validation superimposed upon it.

The proper execution of smart contracts constitutes another pivotal aspect of block processing on the EBF infrastructure. Smart contracts represent self-executing software programs that operate on the blockchain and automate the execution of predetermined rules and conditions. This feature is deemed essential for the EBF platform, as it facilitates the integration of more sophisticated features that can interact with the network in real-time. The execution of smart contracts entails the validation of the input data that is passed through messages, the execution of the underlying code, and the updating of the contract state. The nodes within the network undertake the task of executing smart contracts, where they execute the contract code and arrive at a consensus on the updated contract state.

### State management

State management is another crucial aspect of block processing on the EBF infrastructure. State refers to the current state of the blockchain network, which includes the balances of accounts, the state of contracts, and the current state of the consensus protocol. State management involves updating the network state based on the transactions included in the block and the execution of smart contracts. Nodes in the network perform this process by maintaining a copy of the current state of the network and updating it as new blocks are added to the blockchain. State management plays a vital role in ensuring the consistency and integrity of the blockchain network by ensuring that the current state of the network reflects the latest valid transactions and contract executions.

