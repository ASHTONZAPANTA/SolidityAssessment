# MyToken Smart Contract

## Description Overview
MyToken is a simple ERC20-like smart contract implemented in Solidity. It provides basic functionality to mint and burn tokens. The token is named "ASHTON" with the abbreviation "ASH". This contract is designed for educational purposes and does not include advanced features like transfer functionality or access control.

# How to Install and Run the MyToken Smart Contract

## Prerequisites
- A web browser
- MetaMask extension installed and configured

## Steps

### 1. Open Remix IDE
1. Open your web browser and navigate to [Remix IDE](https://remix.ethereum.org/).

### 2. Create and Paste the Smart Contract Code
1. In the Remix IDE, click the "File Explorer" icon on the left sidebar.
2. Click the "Create New File" button.
3. Name the file `MyToken.sol`.
4. Copy the following code and paste it into the file:
    ```solidity
    // SPDX-License-Identifier: MIT
    pragma solidity 0.8.18;

    contract MyToken {
        string public tokenName = "ASHTON";
        string public tokenAbbrv = "ASH";
        uint public totalSupply = 0;
        mapping(address => uint) public balances;

        function mint(address _address, uint _value) public {
            totalSupply += _value;
            balances[_address] += _value;
        }

        function burn(address _address, uint _value) public {
            if (balances[_address] >= _value) {
                totalSupply -= _value;
                balances[_address] -= _value;
            }
        }
    }
    ```

### 3. Compile the Smart Contract
1. Click on the "Solidity Compiler" icon on the left sidebar.
2. Ensure the compiler version is set to `0.8.18`.
3. Click "Compile MyToken.sol".

### 4. Deploy the Smart Contract
1. Click on the "Deploy & Run Transactions" icon on the left sidebar.
2. Select `Injected Web3` from the "Environment" dropdown (connect MetaMask if prompted).
3. Ensure your MetaMask is connected to a test network (e.g., Ropsten).
4. Make sure `MyToken` is selected in the "Contract" dropdown.
5. Click "Deploy".
6. Confirm the transaction in MetaMask.

### 5. Interact with the Smart Contract
1. After deployment, the contract will appear under "Deployed Contracts".
2. Expand the contract to see the available functions:
    - **Mint tokens**: Enter an address and amount in the `mint` fields, click `mint`, and confirm in MetaMask.
    - **Burn tokens**: Enter an address and amount in the `burn` fields, click `burn`, and confirm in MetaMask.
    - **Check total supply**: Click `totalSupply`.
    - **Check balances**: Enter an address in the `balances` field and click `balances`.

## Conclusion
You have successfully installed and run the MyToken smart contract using Remix and MetaMask. You can now mint, burn, and check balances of your tokens.

# Common Problems and Solutions

## Compilation Errors
**Problem:** Contract doesn't compile.
**Solution:** 
- Ensure Solidity version is `0.8.18`.
- Check for syntax errors.

## MetaMask Connection Issues
**Problem:** Remix can't connect to MetaMask.
**Solution:**
- Log into MetaMask and set it to a test network (e.g., Ropsten).
- Refresh Remix and MetaMask.

## Insufficient Funds
**Problem:** Unable to deploy due to insufficient funds.
**Solution:**
- Get test Ether from a faucet (e.g., Ropsten Faucet).

## Transaction Confirmation Issues
**Problem:** Transactions not confirming.
**Solution:**
- Check and adjust gas fees in MetaMask.
- Retry during less congested times.

## Viewing Token Balances
**Problem:** Balances not updating/displaying correctly.
**Solution:**
- Ensure `mint`/`burn` transactions are confirmed.
- Use the correct address and function (`balances(address)`).

## Security Considerations
**Problem:** Contract lacks security.
**Solution:**
- For production, add security features (e.g., access control).
- Use libraries like OpenZeppelin.

## Network Selection
**Problem:** Deployed on the wrong network.
**Solution:**
- Check MetaMask network before deploying.
- Switch to the correct network and redeploy if needed.

## Gas Limit Issues
**Problem:** Gas limit exceeded.
**Solution:**
- Avoid large token mints/burns in a single transaction.
- Adjust gas limit in MetaMask if necessary.

By addressing these issues, you can successfully deploy and interact with the MyToken smart contract. Always test on a test network first.

# Authors
- Ashton Karl O. Zapanta
- 422002808@ntc.edu.ph
