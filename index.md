- Invoke method (send)
- Call method (call)

![Architecture](ethspoke_arch.png)

## Detailed description

The entity-relationship diagram depicted in figure represents the tables and references existing in the ethspoke and ethsign scoped applications.

| Entity  | Application |Description |
|---|---|---|
|Network|ethspoke|The list of blockchain networks the instance is interacting with.|
|Endpoint|ethspoke|The list of endpoint that are declared within the instance. Endpoints are ethereum nodes and are tied to a specific instance declared by the app administrator. One network may have one or more nodes defined.|
|Smart Contract|ethspoke|The list of Smart Contracts that are defined in terms of bytecode and ABI. Smart contract are not tied to a specific network.|
|Smart Contract Instance|ethspoke|The list of Smart Contracts deployed on chain. May be deployed from the same instance or deployed from another instance and declared in the current instance |
|Method|ethspoke|A method of the smart contract instance, depending on the ABI declared on the smart contract.
|Event|ethspoke|An event that the smart contract instance can fire, depending on the ABI declared on the smart contract.
|Transaction|ethspoke|The log of a transaction invoked from the instance. It can be either a smart contract deployment transaction or a method invocation (send)|
|Key|ethsign|A private and public keypair, and the associated address. The private key is protected by a read ACL that only the ethsign administrator (if any) can modify. The ethsign admin represent the custodian.
|Account|ethsign|The relationship table between keypairs and instance users. Each user is identified depending on the ServiceNow login id and can have zero,  one or more keys assigned to him, with which he will be able to sign transactions. |



![Entity Diagram](ethnow_erd.png)


The ethnow project uses the primitives provided by the [ethjs](https://github.com/ethjs) project.

The following libraries have been adapted/polyfilled to the ServiceNow javascript engine (Rhino 1.7R5 as of the Paris release) and embedded in the applications as script include:

| Library | Purpose |
|---|---|
|ethjs-signer| Sign Ethereum transactions|
|ethjs-account| Generate key pairs and manage accounts|
|ethjs-abi| Encoding and decoding utilities|
|ethjs-format| Payload formatter for the Ethereum RPC layer |


The ethnow spoke talk with the Ethereum node(s) through the node JSON-RPC API.

## How to install 




## How to use

How to install the update set on a new instance (ie dev instance)

How to submit the main workflow using the pre-packaged smart contract

## How to contribute

How to link a new instance to the repo

How to send pull request to the project
