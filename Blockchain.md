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



# Slither

<ins>**Slither is a Solidity static analysis framework for identifying vulnerabilities and bad practices in smart contracts.**</ins>

## Why Slither

- **Security Analysis:** Detect common vulnerabilities like reentrancy bugs and integer overflows.
- **Gas Optimization:** Analyze gas consumption and identify inefficient code patterns.
- **Code Quality Checks:** Identify unused variables and functions for improved code quality.

## Usage

*Setup and usage examples in this repo.*

*install Slither
Begin with installing solc – Solidity compiler:*

```
sudo apt install software-properties-common
```
```
sudo add-apt-repository ppa:ethereum/ethereum
```
```
sudo apt install solc
```

*You should also install the solc-select. It is used for quick installation and switching between Solidity compiler versions.*

Simply run 
```
pip3 install solc-select
```

*After the solc and solc-select are installed with no errors, we can proceed to the Slither installation. It can be done in three ways:*

Using Pip:
``
pip3 install slither-analyzer
``
**check a smart contract using Slither**

*After you defined a contract that you want to check, the easiest way is just to run slither [target]. The target can be specified in several ways:*

**Example: slither SecureContract.sol**

*now put your smart contracts to check the threats and error in in ur smart contract*
*use this smart contrats to checks threats and error also u can use any code which u like to check :-*


```
pragma solidity ^0.4.15;

contract Missing{
    address private owner;

    modifier onlyowner {
        require(msg.sender==owner);
        _;
    }

    // The name of the constructor should be Missing
    // Anyone can call the IamMissing once the contract is deployed
    function IamMissing()
        public 
    {
        owner = msg.sender;
    }

    function withdraw() 
        public 
        onlyowner
    {
       owner.transfer(this.balance);
    }
}
```

*The easiest way to scan the local copy of a smart contract is to run slither with a contract name. Within seconds you will receive the results:*

```
slither mycontract.sol
```
*Now' u will be able to see the whats the threats and error ur smart constract contain (**error  will be in greeen colors**)*

**final interface**

**interface:--**

![image](https://github.com/Rjesh2006/slither_impli/assets/143868643/6cbc9709-4075-4efa-8bd2-056148ba80ea)


# Mythril Summary:

- **Purpose**: Security tool for Ethereum smart contracts.
  
- **Method**: Uses symbolic execution to find vulnerabilities.
  
- **Focus**: Analyzes bytecode for comprehensive assessment.
  
- **Vulnerabilities**: Detects reentrancy bugs, overflows, etc.
  
- **Reports**: Provides detailed insights for action.
  
- **Empowerment**: Secures contracts for safer deployment.

- *mythrill : copy the given command and paste it on ubuntu terminal for solidity security of smart contracts:*
:_⏬
```
sudo apt update
```
# Install solc
```
sudo apt install software-properties-common
sudo add-apt-repository ppa:ethereum/ethereum
sudo apt install solc
```
***1.option***



# Install libssl-dev, python3-dev, and python3-pip
```
sudo apt install libssl-dev python3-dev python3-pip
```
# Install mythril
```
pip3 install mythril
myth version
```

***2. option***

**via Dokcer:**
*All Mythril releases, starting from v0.18.3, are published to DockerHub as Docker images under the mythril/myth name.*
*Docker CE:*

**Pull the latest release of mythril/myth**
```
$ docker pull mythril/myth
```


*Use docker run *mythril/myth* the same way you would use the myth command*
```
docker run mythril/myth --help
docker run mythril/myth disassemble -c "0x6060"

```

```
docker run -v $(pwd):/tmp mythril/myth analyze /tmp/contract.sol
```

```
contract Exceptions {

    uint256[8] myarray;
    uint counter = 0;
    function assert1() public pure {
        uint256 i = 1;
        assert(i == 0);
    }
    function counter_increase() public {
        counter+=1;
    }
    function assert5(uint input_x) public view{
        require(counter>2);
        assert(input_x > 10);
    }
    function assert2() public pure {
        uint256 i = 1;
        assert(i > 0);
    }

    function assert3(uint256 input) public pure {
        assert(input != 23);
    }

    function require_is_fine(uint256 input) public pure {
        require(input != 23);
    }

    function this_is_fine(uint256 input) public pure {
        if (input > 0) {
            uint256 i = 1/input;
        }
    }

    function this_is_find_2(uint256 index) public view {
        if (index < 8) {
            uint256 i = myarray[index];
        }
    }

}

```


***We can execute such a contract by directly using the following command:***

```
$ myth analyze *filepath*
```


**then the final result will be like this:**
![image](https://github.com/Rjesh2006/Solidity_Smart_Contract_Analysis_Tools_and_Techniques/assets/143868643/b539693c-e1a2-4be9-9e7c-80f04d4a10ed)

# Surya

1. **Contract Structure Information**:
    - Provides details about the contracts' structure.
    - Generates inheritance graphs.
    - Supports querying the function call graph.

2. **Visual Outputs**:
    - Outputs a **DOT-formatted graph** of the control flow.
    - Visualizes the relationships between functions and contracts.

3. **Manual Inspection Aid**:
    - Helps auditors understand and analyze Solidity smart contracts.
    - Useful for security assessments and vulnerability detection.


```
sudo apt install npm
```
```
sudo npm version
```


```
npm install -g surya
```
```
npm install -g surya
```
*if it's giving error then:-*
```
sudo su
```

```
npm install -g surya
```

```
apt install graphviz
```

*herw, you have to creat ur own file of .sol::--also you can go through with this given images:🔲*
![image](https://github.com/Rjesh2006/Solidity_Smart_Contract_Analysis_Tools_and_Techniques/assets/143868643/0bfc85fc-7e87-4191-be26-fd3118c0792f)


```
surya ftrace APMRegistry:: rajesh2.sol
surya ftrace <function_identifier> <function_visibility_restrictor> <files..>
```


```
surya parse rajesh2.sol
```
***after putting this command you will be get this interface***

*like a tree flow result:here as you ca see that:---*
![Screenshot from 2024-04-12 21-46-57](https://github.com/Rjesh2006/Solidity_Smart_Contract_Analysis_Tools_and_Techniques/assets/143868643/3de5e8f7-fe9d-494c-bf65-8a473184b7ef)

![Screenshot from 2024-04-12 21-47-07](https://github.com/Rjesh2006/Solidity_Smart_Contract_Analysis_Tools_and_Techniques/assets/143868643/0d27b06d-283d-4108-9a36-344ba5761009)


