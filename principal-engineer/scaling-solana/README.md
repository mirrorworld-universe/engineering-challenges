<center>
<a center href="https://mirrorworld.fun">
  <img src="../../assets/mirroworld.png" width="100"/>
</a>
</center>
<center><h1><code>Principal Engineering Challenge: Scaling Solana at Application Level</code></h1></center>

## Problem statement

MirrorWorld's blockchain marketplace is built on the Solana NFT protocol known as [Metaplex]. Where as Metaplex provides a protocol by which NFTs on [Solana] can be standardized, it has also deployed a few general purpose contracts to aid this effort, namely:
1. [Auction House program]
2. [Token Metadata program]
3. [Token Vault program]
4. [Token program] (Also generally used for [SPL tokens])

Because Solana recommends decentralized applications to deploy their NFTs using their provisioned program addresses, this can present two main problems when building applications on Solana at scale:
  - Repeated work done by multiple clients to consume, serialize and deserialize the accounts data from Solana.
  - Once the volume of accounts data being read from the chain grows in size, so does the client payload increase in size. It's been estimated to reach sizes of up to 20MB in a single client download on Solana devnet.

## Challenge
### Solution design question
These questions can be answered in writing. You may also use diagrams to support your writing
1. What solutions do you propose to enable the client (web application or mobile application) to consume on-chain data in it's current state without the double payload on the client?
2. Is it possible to only track addresses we pre-define?
  1. How can this account indexing be done?
  2. What advantages does this present for your system?
  3. How can we scale this solution for 1,000,000 users?
  4. What challenges does this present?
3. Briefly explain the Solana accounts programming model. What other applications can this programming paradigm be consumed?

### System design & Coding questions
Design a service that synchronizes the state of a related set of accounts from Solana. Your system should provide a service with an endpoint that accepts an account address and returns the most recent transactions related to that account. Your system should query and store the list of accounts to track from Solana.

### Requirements
#### Coding
1. Write a Solana program in Rust that indexes a list of addresses that should be tracked. Your client application should track the list of accounts from this program.
2. Create a service that provides an API that accepts an account address and returns the most recent 20 transactions related to that account.
  1. You may use diagrams to showcase the flow of data between services and endpoints to explain the flow of your data if necessary.
  2. You may use any programming language of your choice (We recommend using [Node.js] or [Golang])
#### Submission
1. Submit your solution to the MirrorWorld Engineering Challenges repository under the Principle Engineer directory and open a pull request with the branch name: `principle_<YOUR_NAME>`
   
#### Self-review
1. Make sure your code runs before submitting the pull request.
2. Record any potential challenges your system may face, and how to protect it against them.
3. Your written solutions should be added in the README.md of your submission.
4. When opening a pull request for your solution, please tag @codebender828 as a reviewer


### Advanced (optional)
1. How can assets on one chain (e.g. Solana) be cross-represented on a different blockchain (e.g. Ethereum / Polygon / StarkEx)?
2. Design a high-level protocol to represent such a cross-chain interoperability. (We would be interested to know how Layer 2 blockchains can achieve interoperability with Layer 1 chains).

### Support / Questions
1. In case of any questions, please contact me at jonas@mirrorworld.fun or open a GitHub issue to this repository or reach me on Telegram (@jesus_jonas)


<!-- Sites -->
[Metaplex]: https://metaplex.com

<!-- Source code -->
[Auction House program]: https://github.com/metaplex-foundation/metaplex-program-library/tree/master/auction-house
[Token Metadata program]: https://github.com/metaplex-foundation/metaplex-program-library/tree/master/token-metadata
[Token Vault program]: https://github.com/metaplex-foundation/metaplex-program-library/tree/master/token-vault
[Token program]: https://github.com/solana-labs/solana-program-library/tree/master/token
[SPL tokens]: https://spl.solana.com/


<!-- Source code -->
[Node.js]: https://nodejs.org/en/
[Golang]: https://go.dev/


<!-- Chains -->
[Solana]: https://solana.com
[Ethereum]: https://ethereum.org