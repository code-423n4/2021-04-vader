# Vader contest details
- 24 ETH main award pot
- 3 ETH gas optimization award pot
- 1000 VETH bonus pot
- Join [C4 Discord](https://discord.gg/EY5dvm3evD) to register
- Submit findings [using the C4 form](https://c4-vader.netlify.app/)
- [Read our guidelines for more details](https://code423n4.com/compete)
- Starts 2021-04-22 00:00:00 UTC
- Ends 2021-04-28 23:59:00 UTC

This repo will be made public before the start of the contest.

[ ⭐️ SPONSORS ADD INFO HERE ]

### Overview
VADER Protocol is an implemenation of the ideas discussed here:
https://docs.google.com/document/d/1O10Pay1ZjBJwEjeHulp924-Cuustjatl7OoH-sGkDs8/edit?usp=sharing

### USDV
* Same concept as LUNA<>UST
https://terra.money/Terra_White_paper.pdf

### Liquidity
* Same concept as THORChain CLP 
https://github.com/thorchain/Resources/blob/master/Audits/THORChain-Gauntlet-CLPReport-Nov2020.pdf

### Synths
* Synthetic Assets minted from liquidity collateral using a formula that mints on the assymetric value of the deposited asset. 

### Lending
* Borrowing debt is faciliated by borrowing BASE collateral from the protocol, then paying it back, but price in Debt Value. Thus the protocol takes the short position on its own asset. 

### Non-standard ERC20
* VADER, USDV, SYNTHS all employ the `transferTo()` function, which interrogates for `tx.origin` and skips approvals. The author does not subscribe to the belief that this is dangerous, although users should be warned that they can be phished and stolen from *if they interact with attack contracts*. Since all these assets are intended to be used in the system itself, the risk of a user interacting with an attack contract is extremely low. 
* There are some discussion whether `tx.origin` will be deprecated, but the author believes that there is a really low chance it will, and if so, it will likely be replaced with `tx.orgin = msg.sender` which means the contracts will still work. Compatibility function have been added to anticipate this. 

### Unique
VADER is an implementation of various ideas across the space. There is nothing *new*, just a more cohesive system that takes advantage of several key concepts. 

### Known Issues (deviations from spec)
*will be updated if this list changes*
1) USDV staking is still present in the code, this will be removed for SYNTH-only staking in a separate Vault. 
2) Anchor pool creation is not curated
3) Interest Rate payment is not yet automatic
4) Interest Rate deductions not yet added
5) Liquidation logic not yet added
6) Purge Member logic not yet added
7) DEPLOYER privs not yet added
8) Full DAO functionality not yet added
9) Liquidity Limits not yet added
10) Various other small features

### Areas of Review

Ideally, the following is reviewed:
* Any attack vectors that can siphon funds from the system
* Any attack vectors using flash loans
* Any attack vectors by Anchor Price manipulation
* Any attack vectors by VADER<>USDV mint/burn




