# Monero Detail Design
A technical guide for beginner, intermediate, and advanced users.

This is unofficial documentation. Use it with caution.

## Introduction
In the digital era, it is easy to make endless copied of information, with eqully endless alterations. For a currency to exist digitally and be widely adopted, it users must belive its supply is strictly limited and not a counterfiet. To accomplish that without requiring any collaboration of any third party like a central authority, its supply and complete transaction history must be publicly verifiable and auditable. This is where the blockchain technology allows data to be registered in easily accessible database and cryptographiclly secured. The blockchain would be virtually immutable and unforgeable, with legitimacy that cannot be disputed by any party. 

Crypotcurrencies store transactions data in the blockchain, which acts as a `public ledger`. Bitcoin is an example of implemntation of an open blockchain. The transaction histories of its users are publicly broadcasted. With the recent development of blockchain analysis tools, it would be possible to analyze the flows of funds and to a large extend link true senders with the receivers. Therefore this would hinder privacy aspects. 

Monero cryptocurrency attemps to tackle the limited privacy on an open blockchain by ringCT to obsecures identities of the sender because of it only proves that a signer belongs to a group and by authenticating the dispersal of funds in each transaction with ringCT. With these methods there ar no effective way to link receivers or trace the origin of funds. 

Additially, transaction amounts in the Monero blockchain are concealed behind cryptographic constructions, rendering currency flow opaque. This allows a high level of anonymity in cryptocurency transafctions. 

### Abbreviations
| Abbreviations | Descriptions                                           |
| ------------- | ------------------------------------------------------ |
|RingCT         | Ring Signatures

### Definitions
| Definitions   | Descriptions                                           |
| ------------- | ------------------------------------------------------ |
|Address        | Also refer to wallet addres for Monero is a set of 95 characters starting with a '4'. For instance 44AFFq5kSiGBoZ4NMDwYtN18obc8AemS33DBLWs3H7otXft3XjrpDtQGv7SqSsaBYBb98uNbr2VBBEt7f2wfn3RVGQBEP3A.|
|Address Book   | An Address Book allow you to traslate I2P websites/services that use the `.i2p`top-level domain into an address that I2P network will understanand. |
|Atomic Untis   | It is refering to the smallest fraction of 1 XMR. One atomic unit is currently 1e-12 (0.000000000001 XMR, or one piconero). |
|Base32 Address | Is a shrtened, encoded version of an I2P address. The Base32 address is the first part in `.b32.i2` hostname. 
Example: `i35yftyyb22xhcvghmev46t5knefur5v66qzekkajatwfwhyklvq.b32.i2p`
Where `i35yftyyb22xhcvghmev46t5knefur5v66qzekkajatwfwhyklvq` is the Base32 address. A Base32 address is a 52 character Base32 encoded represntation of the full SHA-256 of an I2P Base64 address. | 
|Blockchain     | A distributed database that continously grows with a record of all transaction that have occured with given cryptocurrency. The database often refer as a ledger because the dat contains a larg list of transactions that have taken place. |


## Specification
* Release Date: 18-April-2014
* Blockchain Protocol: Proof of Work (PoW)
* PoW algorithm: CryptoNightV8 [1]
* Usage: Digital Currency
* Cryptocurrency Name: Monero
* Cryptocurrency Symbol: XMR
* Max supply: 18.4 Million XMR + 0.3 XMR/minute 
* Block reward: Smoothly varying
* Block time: 120 seconds
* Difficulty: Retargets at every block 
[1] CPU + GPU mining
[3] Use a recurrence relation. Block reward = (M - A) * 2^-20 * 10^-12, where A = current circulation. 

## Basic Concepts
### Modular Aritmatic
### Elliptic Curve Cryptography
### Curve Ed25519
## Ring Signatures
Ring singnatures are compoesed of a ring and a signature. Each `signature` is generated with a single private key and a set of unrelated public keys. Each `ring` is the set of public keys comprising the private key's public key, and the set of unrelated public keys. Somebody verifying a signature would not be able to tell which ring member corresponds to the private key that created it. 

Ring signatues were originally called `Group Signatures` becasue they were thought of as a way to prove a signer belong to a group, without necessary identifiying thim. In context of Monero they will allowy for unforgeable, singer-ambigous transactions that leave currency flows large untraceable.

Ring signature advantage:
* *Singer Ambiguity* An observer should not be able to determine the origin of the funds since each transaction signs with a group of signatures (randomly selected). This would obsecure the original sender.

* *Linkability* If private key is used to sign two different massages then the message will become linked. This is a ring member whose public key has been mixed into different signatures. Therefore it cannot be linked directly instead it would only be probabilty of the signers. The linkability propertiy does not apply to non-signing public keys.

* *Unforgeability* No attacker can forge a signature except with negligible probabilty. A certain ring schemes are strong againts adaptive chosen-massage and adaptive chosen public-key attacks. An attacker who can obtain legitamte signature from messages and corresponding to specific public keys in rings of his choice cannot discover how to forge the signature of even one massage. This is called *existential uforgeability*. 

### Likable Spontaneous Anonymous Group (LSAG)
### Back's Linkable Spontaneous Anonymous Group (bLSAG) signatures
### Borromean ring signatures
## Pedersen Commitments
### Pedersen Commitments
### Amount Commitments
### Range Proofs
### Range Proofs in a blockchain
## Monero Transactions
### User Keys
### One-time Addresses
### Subaddress
### Integrated Addresses
### Transaction Types
### RingCT of Type ```RCTTypeFull```
### RingCT of Type ```RCTTypeSimple```
### Summary: Monero Transactions
## Monero Blockchain
### Digital Currency
### Difficulty
### Money Supply
### Blockchain Structure

## References
1. June 26, 2018 - Zero To Monero: First Editon by Kurnt M. Alonso
