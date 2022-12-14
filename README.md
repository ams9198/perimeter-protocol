# perimeter-core

This repository contains the contracts for the Perimeter protocol.

## Getting started

```sh
npm install
```

Copy .env.example and update with appropriate values

```sh
cp .env.example .env
```

## Running a node

```sh
npx hardhat node
npx hardhat run scripts/deploy.ts
```

## Generating Docs

Documentation is generated by [solidity-docgen](https://github.com/OpenZeppelin/solidity-docgen)

```sh
npm run docs

# or

npx hardhat docgen
```

## Testing

```sh
npm test

# or

npx hardhat test
```

### Gas usage reports

```sh
npm run test:gas

# or

REPORT_GAS=true npx hardhat test
```

### Code Coverage

```sh
npm run test:coverage

# or

npx hardhat coverage
```

### Hardhat Tasks

There are several hardhat tasks to allow for easy modification of the contracts.

Updating the ServiceConfiguration:

- setPaused
- setLiquidityAsset
- setLoanFactory
- setTosAcceptanceRegistry

You can find complete instructions for how to run each command by running the following:

```sh
npx hardhat setPaused --help
```

Here is an example command to pause a hypothetical contract:

```sh
npx hardhat setPaused --address 0x5FbDB2315678afecb367f032d93F642f64180aa3 --paused true
```

### Getting a Circle Verite Verification Result

Update the config in `scripts/verite-verify.ts` with the appropriate values, then run

```sh
npx hardhat run scripts/verite-verify.ts
```

This will print out a verification result that can be send to the `verify()` method on the given contract.

### Etherscan Verification

Contract source can be uploaded and verified to Etherscan. Update `.env` to include your etherscan API key.

For each deployed contract, run the following:

```
npx hardhat verify --network goerli CONTRACT_ADDRESS
```

There are three contracts that require constructor arguments:

- WithdrawControllerFactory
- PoolControllerFactory
- PoolFactory

```
npx hardhat verify --network goerli CONTRACT_ADDRESS arg1 arg2 arg3
```
