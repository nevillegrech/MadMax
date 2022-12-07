Note: you need to clone this repo using the `--recursive` flag since this repo has submodules, e.g.,

`git clone git@github.com:nevillegrech/MadMax.git --recursive`

# MadMax 
![License](https://img.shields.io/github/license/nevillegrech/MadMax) ![GitHub Repo stars](https://img.shields.io/github/stars/nevillegrech/MadMax) [![Twitter Follow](https://img.shields.io/twitter/follow/neville_grech.svg?style=social)](https://twitter.com/neville_grech)

Madmax consists of a series of analyses and queries that find gas-focussed vulnerabilities in Ethereum smart contracts. The analyses are performed on the [Gigahose](https://github.com/nevillegrech/gigahorse-toolchain) IR, which is lifted from Ethereum bytecode. The first version of MadMax used [Vandal](https://github.com/usyd-blockchain/vandal).

# How to use
First follow the instructions in [gigahorse-toolchain](gigahorse-toolchain/README.md) for instructions on installation of [Gigahorse](https://github.com/nevillegrech/gigahorse-toolchain). In a nutshell, this requires the installation of the Souffle Datalog engine, custom functors and Boost.

In order to run MadMax using Gigahorse, you can use the following incantation:

`gigahorse-toolchain/gigahorse.py -C madmax.dl <contract.hex>`

Where `<contract.hex>` is a compiled Ethereum contract, or a directory of contracts. If you're running this for the first time it will take longer due to compilation of Datalog files. The output of the analysis results can be found under `.temp/**/out/*.csv` and `results.json`. A summary is also printed to the screen.

To see whether an individual contract is flagged or not if, check whether there are any entries inside the `WalletGriefing`, `UnboundedMassOp` and `OverflowLoopIterator` relations.


# Live Deployment
Some of the techniques developed in the MadMax project are now used in [Dedaub Watchdog](https://dedaub.com/watchdog).

# Publications

MadMax: surviving out-of-gas conditions in Ethereum smart contracts
Neville Grech, Michael Kong, Anton Jurisevic, Lexi Brent, Bernhard Scholz, and Yannis Smaragdakis
Proceedings of the ACM in Programming Languages (OOPSLA) 2018
[PDF](https://www.nevillegrech.com/assets/pdf/madmax-oopsla18.pdf)

🏆 Distinguished Paper 🏆

MadMax: Analyzing the Out-of-Gas World of Smart Contracts
Neville Grech, Michael Kong, Anton Jurisevic, Lexi Brent, Bernhard Scholz, and Yannis Smaragdakis
Communications of the ACM 2020
[PDF](https://www.nevillegrech.com/assets/pdf/madmax-cacm.pdf)

🏆 CACM research highlight 🏆


[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/LENrSCeoTqg/0.jpg)](https://www.youtube.com/watch?v=LENrSCeoTqg)











