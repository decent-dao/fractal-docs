---
description: Fractal Governance Types
---

## Multisig

A multisig Safe is essentially just a Safe multisig wallet, no different than deploying via [the Safe app itself](https://app.safe.global), except that Fractal adds an on-chain name and optional Snapshot space to be associated with it.

For multisig *sub-Safes*, Fractal also attaches a [Safe guard contract](https://docs.safe.global/learn/safe-core/safe-core-protocol/guards) which allows the ability of the parent-Safe to vote to freeze the multisig from executing transactions.

---

## Token Voting

A Token Voting Safe is a Safe{Wallet} contract with an Azorius [module](https://docs.safe.global/learn/safe-core/safe-core-protocol/modules) which allows for submitting and voting on proposals by token holders.

Our [Azorius module](https://github.com/decent-dao/fractal-contracts) conforms to Safe's [Zodiac pattern](https://gnosisguild.mirror.xyz/OuhG5s2X5uSVBx1EK4tKPhnUc91Wh9YM0fwSnC8UNcg), and has been audited by [Halborn](https://www.halborn.com/), the results of which can be found [here](https://app.fractalframework.xyz/docs/fractal_audit.pdf).

There are no signers on this Safe{Wallet}, all transaction executions are performed via the Safe module contract after a proposal is successfully voted on.

In the case of Token Voting *sub-Safes* Fractal also attaches a Safe guard contract to allow for freezing, in the same way as a multisig sub-Safe.

---

## NFT voting

NFT-based voting allows for holders of specific ERC-721 tokens to vote on proposals, in much the same way as Token Voting governance allows for ERC-20 holders to vote.

This allows for multiple NFTs to be "registered" on the strategy, with optional voting weights for each NFT collection given voting power.

NFT voting *sub-Safes* also have an associated Freeze Guard contract, identical to Token Voting sub-Safes.