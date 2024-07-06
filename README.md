
Smart Health Report Generating System:
A decentralized system for managing Digital Health Records using Blockchain and IPFS.

# Requirements
 Instructions to install all required dependencies are given below.

# Ganache
1. Ganache is a personalized blockchain for Ethereum development. It can be used to run tests, execute commands, and inspect states while controlling how the chain          operates.
2. Go to [Ganache homepage](https://www.trufflesuite.com/ganache) and download.

# IPFS
1. Go to [go-ipfs](https://dist.ipfs.io/#go-ipfs) and install go ipfs.  Using IPFS through the command-line allows you to do everything that IPFS Desktop can do, but at    a more granular level since you can specify which commands to run.

# Metamask
1. Metamask is a browser extension available for Google Chrome, Mozilla Firefox and Brave Browser.
2. Go to the this [link](https://metamask.io/) and add Metamask to your browser.

# Node js
1. Node.js is designed to build scalable network applications.
2. Go to the this [link](https://nodejs.org/en/download/) and install node js.


# Getting the DApp running

### Configuration

#### 1. Ganache
 *  New Workspace
 *  AddProject
 *  Select truffle-config.js in Project Directory
 *  Save Workspace

  - Open Ganache and click on settings in the top right corner.
  - Under **Server** tab:
    - Set Hostname to 127.0.0.1 -lo
    - Set Port Number to 7545
    - Enable Automine
  - Under **Accounts & Keys** tab:
    - Enable Autogenerate HD Mnemonic

#### 2. IPFS
  - Fire up your terminal and run `ipfs init`
  - Then run 
    ```
    ipfs config --json API.HTTPHeaders.Access-Control-Allow-Origin "['*']"
    ipfs config --json API.HTTPHeaders.Access-Control-Allow-Credentials "['true']"
    ipfs config --json API.HTTPHeaders.Access-Control-Allow-Methods "['PUT', 'POST', 'GET']"
    ```

    > Note: If you face any issues with the above command on windows, try using command prompt and escape sequences or git bash.
#### 3. Metamask
  - After installing Metamask, click on the metamask icon on your browser.
  - Click on __TRY IT NOW__, if there is an announcement saying a new version of Metamask is available.
  - Click on continue and accept all the terms and conditions after reading them.
  - Stop when Metamask asks you to create a new password. We will come back to this after deploying the contract in the next section.
  
### Smart Contract

1. Install Truffle using `npm install truffle -g`
2. Compile Contracts using `truffle compile`

#### 1. Starting your local development blockchain
  - Open Ganache.
  - Make sure to configure it the way mentioned above.
  
1. Open new Terminal and deploy contracts using `truffle migrate`
2. Copy deployed contract address to src/app.js 
![alt text](https://raw.githubusercontent.com/SuyashMore/SwasthyaChain/master/images/ganace-contracct.png)

```js
// src/js/app.js  line number 11
var agentContractAddress = '0x75E115394aacC7c6063E593B9292CB9417E4cbeC';
```

3. If you change contents of any contract , replace existing deployment using `truffle migrate --reset`
> Note :  reset of the contract will change the contract Address which needs to be updated in src/app.js

### Running the dApp

#### 1. Connecting Metamask to our local blockchain
  - Connect metamask to localhost:8485
  - Click on import account
  ![alt text](https://raw.githubusercontent.com/SuyashMore/SwasthyaChain/master/images/meta-1.png)
  - Select any account from ganache and copy the private key to import account into metaMask
  ![alt text](https://raw.githubusercontent.com/SuyashMore/SwasthyaChain/master/images/con-g1.png)

#### 2. Starting IPFS 
  - Start the IPFS Desktop Application

  
#### 3. Start a local server
  - Open a new terminal window and navigate to `/YOUR_PROJECT_DIRECTORY/app/`.
  - Run `npm start`.
  - Open `localhost:3000` on your browser.
  - That's it! The dApp is up and running locally.
  
#### 4. Changes in IPFS infura Api

  - This API is paid so use your credit card and get a trial of this API, after getting the trial do not worry this    project wont exceed the limit, just get a trial you wont be charged thats it.
  -  Create a account on https://www.infura.io/.
  -  Create a new key and select these options from drop down menu. (Network : IPFS, Project name : " " of your choice)
  -  After creating a key you will find "Project ID" and "API Secret Key".
  -  Copy these 2 keys and paste it in line no. 305 and 306 of doctor.html
  



