# Smart Contract Deployment Instructions

## Issue Resolution
The current smart contract at address `0x2662b183bC1883e15B8E4D1E8DE1Da5ca126A626` is experiencing a `CALL_EXCEPTION` error due to corrupted contract state. You need to redeploy the contract to resolve this issue.

## Steps to Deploy New Contract

### 1. Open Remix IDE
- Navigate to https://remix.ethereum.org/
- Create a new file called `GlobalStorage.sol`

### 2. Copy Contract Code
Copy the entire contract code from `contracts/GlobalStorage.sol` into the Remix editor.

### 3. Compile the Contract
- Go to the "Solidity Compiler" tab
- Select compiler version `0.8.19` or higher (but less than `0.9.0`)
- Click "Compile GlobalStorage.sol"
- Ensure there are no compilation errors

### 4. Deploy to Sepolia
- Go to the "Deploy & Run Transactions" tab
- Set Environment to "Injected Provider - MetaMask"
- Ensure MetaMask is connected to Sepolia testnet
- Select `GlobalStorage` contract from the dropdown
- Click "Deploy"
- Confirm the transaction in MetaMask

### 5. Copy New Contract Address
- After successful deployment, copy the new contract address from Remix
- The address will appear in the "Deployed Contracts" section

### 6. Update Frontend
- Open `src/App.jsx`
- Find the line: `const [contractAddress, setContractAddress] = useState("")`
- Replace the empty string with your new contract address:
  ```javascript
  const [contractAddress, setContractAddress] = useState("YOUR_NEW_CONTRACT_ADDRESS")
  ```

### 7. Test the Application
- Refresh your browser
- Try uploading a file to test the new contract
- The `getMyFiles()` error should now be resolved

## Important Notes
- Make sure you have sufficient Sepolia ETH for deployment (get from faucet if needed)
- The new contract will be empty - previous files won't be accessible
- Save your new contract address for future reference
- Update any documentation with the new contract address

## Verification
After deployment, you can verify the contract is working by:
1. Connecting your wallet to the app
2. Uploading a test file
3. Checking that the file appears in your "My Files" section without errors