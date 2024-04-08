# **Blockchain**
Blockchain technology is a decentralized and secure digital ledger that records transactions across multiple computers. It was first introduced with the creation of Bitcoin in 2008. 


<img src="https://github.com/Shantanu2911/Notes/assets/143939657/47c12c8a-6d9b-4375-9d6a-dd07ec1dedba" width="45%" height="45%">    <img src="https://github.com/Shantanu2911/Notes/assets/143939657/0505bd3e-a7a9-46f0-8029-8698d94c5cbe" width="40%" height="40%">


## Key concepts
- Blockchain is a secure and distributed ledger that consists of interconnected blocks. 
- It was first introduced in 2008 by an individual or group known as Satoshi Nakamoto.
- Blockchain technology is the underlying technology for cryptocurrencies like Bitcoin.
- Blockchain can be implemented as a public or private blockchain, depending on the use case.
- Blockchain technology offers enhanced security and transparency in various industries.
- The blockchain ensures the integrity and immutability of data through cryptographic hashing.
- Peer-to-peer database synchronization is used to update and improve databases across a network of peers.
- Blockchains are decentralized and eliminate risks associated with centralized data storage.
- Hard forks in the blockchain industry can lead to the creation of separate blockchain versions.
- Decentralization and public-key cryptography are key components of blockchain security.

# Solidity-sec-audit

## Prerequisites
  - Install [Docker](/Docker.md)
  - Pull [devopstestlab/solgraph](https://www.npmjs.com/package/solgraph) : `docker pull devopstestlab/solgraph`.
    
## Create the smart contract in solidity:
```
sudo mkdir data
cd data
sudo vi MyContracts.sol
```
Run this smart contract in the docker image we just pulled:
```docker run -it --rm -v $PWD:/data devopstestlab/solgraph```

View the image using: `xdg-open MyContracts.sol.png`

![image](https://github.com/Shantanu2911/Notes/assets/143939657/75b72907-3b87-4849-8f84-47bb7af6b675)



## Solidity smart contracts security audit images:

**Slither :** [click here](https://github.com/crytic/slither) to view the official documentation.


## Using slither:
```
docker pull trailofbits/eth-security-toolbox
```
Create a new mycontract.sol (Voting Blockchain):
```solidity
contract MyContract {
  uint balance;

  function MyContract() {
    Mint(1000000);
  }

  function Mint(uint amount) internal {
    balance = amount;
  }

  function Withdraw() {
    msg.sender.send(balance);
  }

  function GetBalance() constant returns(uint) {
    return balance;
  }
}
```

Mount the contracts data directory to the container and run it:
```
$ docker run -v $(pwd)/contracts:/contracts/ trailofbits/eth-security-toolbox bash -c "solc /contracts/mycontract.sol"
```
![image](https://github.com/Shantanu2911/Notes/assets/143939657/325b132e-502a-45ab-b400-b2832538fb6c)



Note that one could've directly opened an interactive terminal using `docker run -it -v $(pwd)/contracts:/contracts/ trailofbits/eth-security-toolbox bash`
