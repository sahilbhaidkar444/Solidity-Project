# Lottery Contract Project

This is a simple Ethereum smart contract written in Solidity for conducting a lottery. The contract allows participants to enter the lottery by sending 1 ether, and the winner is chosen randomly among the participants when the manager calls the `selectWinner` function.

## License

This project is licensed under the terms of the GNU General Public License v3.0 (GPL-3.0). See the [LICENSE](LICENSE) file for details.

## Prerequisites

- `Solidity >=0.7.0 <0.9.0`

## Contract Details

### `Lottery` Contract

- `manager`: Address of the manager who deploys the contract.
- `participants`: Array of addresses representing participants who entered the lottery.

#### Constructor

- Initializes the `manager` variable with the address of the deployer.

#### `receive` Function

- Allows participants to enter the lottery by sending 1 ether.
- Ensures the sent value is exactly 1 ether.

#### `getBalance` Function

- Retrieves the balance of the contract.
- Accessible only by the manager.

#### `random` Function

- Generates a pseudo-random number using block information and participant count for fairness.

#### `selectWinner` Function

- Allows the manager to select a winner from the participants.
- Requires at least 3 participants.
- Chooses a random participant as the winner.
- Transfers the entire contract balance to the winner.
- Resets the participants array.

## Usage

1. Deploy the `Lottery` contract to an Ethereum network.
2. Participants can enter the lottery by sending 1 ether to the contract address.
3. The manager calls the `selectWinner` function to choose a winner after at least 3 participants have entered.
4. The winner receives the entire contract balance.

## How to Deploy

To deploy the contract, follow these steps:

1. Compile the contract using a Solidity compiler compatible with the specified version.
2. Deploy the compiled bytecode to the Ethereum network using tools like Remix, Truffle, or Hardhat.

## Contributing

Contributions are welcome! Feel free to open an issue or submit a pull request.

## License

This project is licensed under the terms of the GNU General Public License v3.0 (GPL-3.0). See the [LICENSE](LICENSE) file for details.
