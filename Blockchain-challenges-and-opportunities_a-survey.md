---
creation date: 22/02/2022 
modification date: 22/02/2022 22:32
Sources: https://allquantor.at/blockchainbib/pdf/zheng2018blockchain.pdf
---
This article is composed of the notes I have taken reading this paper:
https://allquantor.at/blockchainbib/pdf/zheng2018blockchain.pdf

---
[Index](index.html)

---
# Blockchain challenges and opportunities - a survey
## Architecture
### Block
- Composition![Block Schema](docs\assets\images\Pasted-image-20220222224720.png)
	- *Header*
		- Block version: set of block validation rules to follow
		- Parent block hash: 256-bit hash value, points to previous block
		- Merkle tree root hash: hash value of ALL transactions inside the block
		- Timestamp: current timestamp as seconds since 1970-01-01T00:00 UTC
		- nBits: current hashing target (compact format)
		- Nonce: 4-byte field, starts with 0, increase for every hash calculation
	- *Body*
		- Transaction counter
		- Transactions
			- Max # that block can contain depends on *block size* and *transaction size* 
			- Authenticity validated through asymmetric cryptography mechanism
### Digital Signature
- User owns pair of public & private keys
	- Private key = user signature on transactions, encrypt the file hash, **signing phase**
	- Public key = available to anyone, decrypt the hash and verify it is the same as the hashed file, **verification phase**
### Blockchain properties
- Decentralization: P2P
- Persistency: very hard to tamper because blocks are validated by other nodes and transaction checked
- Anonymity: user can generate any number of address
- Auditability: every transaction is recorded so that anyone can verify and trace previous records
### Blockchain system classification
- Criterias
	- Consensus determination: who can take part in the consensus process
	- Read permission: who can read the transactions
	- Immutability: quantity of nodes needed to tamper/reverse the blockchain
	- Efficiency: ressources needed to propagate transactions/blocks through the nodes
	- Centralized: level of amalgamation of the nodes
	- Consensus process: do you need special rights to access the consensus process 
- | Property                | **Public**         | **Consortium**           | **Private**              |
| ----------------------- | -------------- | -------------------- | -------------------- |
| Consensus determination | All miners     | Selected nodes       | 1 org                |
| Read permission         | Public         | Public or restricted | Public or restricted |
| Immutability            | Extremely high | Can be tampered      | Can be tampered      |
| Efficiency              | Low            | High                 | High                 |
| Centralized             | Very low       | Medium               | High                 |
| Consensus process       | Permissionless | Permissioned         | Permissioned         | 

## Consensus Algorithm
Refers to the Byzantine Generals problem
-> How to create a global consensus in a no-trust environment ?
### Proof of Work POW
- Requires a complicated computational process for authentication (**mining**)
	- 1. Each node (**miner**) is calculating hash value of constantly changing block header
	- 2. Someone needs to find hash value equal or smaller to a given value everyone agreed on 
	- 3. When one find the right value, every node must confirm its correctness
	- 4. Transactions in the block are verified
	- 5. This collection of transactions that were hashed is approved and create a new block in the chain

- Edge case: When 2 valid blocks are generated at the same time 
	- A fork of the main chain is created for every identical block
	- The chain that gets longer the fastest is the one that is chosen as the main one
	- Blocks of the other chains are abandoned and considered orphans
### Proof of Stake POS
- Nodes have to prove the ownership of an amount of currency to mine
### Proof of Burn POB
- Nodes have to sacrifice tokens to a public address to increase their luck of having to opportunity of mining blocks without needing powerful hardwares 
### Alternatives "Proof of"
- Proof of Activity : mined blocks need to be signed by N miners to be valid
- Proof of Capacity : allocate large hard drive space to mine the block
### Byzantine Agreement protocols
#### **Practical Byzantine Fault Tolerance PBFT**
- New block is determined during a **round**
	- 1. Primary node is selected, it will order the **transaction** (3 phases)
		- Pre-prepared
		- Prepared
		- Commit
	- A node can enter the next phase if it is validated by 2/3 of all nodes
- <- Every node needs to be known to the network
- ![PBFT](docs\assets\images\Pasted-image-20220223141459.png)
#### **Stellar Consensus Protocol SCP**
- Gives participants the right to choose which set of other nodes to believe

| Property                     | PoW                   | PoS         | PBFT                    | DPOS             | Ripple                    | Tendermint                     |
| ---------------------------- | --------------------- | ----------- | ----------------------- | ---------------- | ------------------------- | ------------------------------ |
| Node identity management     | Open                  | Open        | Permissioned            | Open             | Open                      | Permissioned                   |
| Energy saving                | No                    | Partial     | Yes                     | Partial          | Yes                       | Yes                            |
| Tolerated power of adversary | < 25% computing power | < 51% stake | < 33.3% faulty replicas | < 51% validators | < 20% faulty nodes in UNL | < 33.3% byzantine voting power |
| Example                      | Bitcoin               | Peercoin    | Hyperledger             | Bitshares        | Ripple                    | Tendermint                     |
 
## Applications of Blockchain
!(Applications of Blockchain)[docs\assets\images\Pasted-image-20220223145710.png]
