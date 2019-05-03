# File-Storage-Dapp
Link to Project:

https://drive.google.com/open?id=1I35Mb3KElw8TnKDcZrbNIY8R44OKS99m

The application takes files and uploads them to IPFS, and stores the hash locations of the files on a local blockchain running with Ganache.




How to Run this Program:

Setup of Virtual Machine running Ubuntu 18.04.

Install Google Chrome with the following commands in Terminal:
	$ wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo apt-key add -
	$ echo 'deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main' | sudo tee /etc/apt/sources.list.d/google-chrome.list
	$ sudo apt-get update 
	$ sudo apt-get install google-chrome-stable

With Chrome installed, add the MetaMask extension from the following link:
	https://chrome.google.com/webstore/detail/metamask/nkbihfbeogaeaoehlefnkodbefgpgknn?hl=en
	Once installed, setup up MetaMask with a password

Install Node.js & Node Package Manager (npm) with the following commands in Terminal:
	$ curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
	$ sudo apt-get install -y nodejs
	$ sudo npm install npm --global

Install Ganache with the following steps:
	Go to: https://github.com/trufflesuite/ganache/releases
	Download "ganache-1.2.1-x86_64.AppImage"
		Navigate to the downloaded file, right click on it, and select Properties
		Go to the "Permissions" tab and select the box next to Execute (Allow executing file as program)
	Double click on the .AppImage File to run Ganache

Install git with the following command in Terminal:
	$ sudo apt-get install git-core

Install Truffle Framework with the following command in Terminal:
	$ sudo npm install -g truffle

Install the IPFS API with the following command:
	$ sudo apt-get install golang-go -y
	$ wget https://dist.ipfs.io/go-ipfs/v0.4.10/go-ipfs_v0.4.10_linux-386.tar.gz
	$ tar xvfz go-ipfs_v0.4.10_linux-386.tar.gz
	$ sudo mv go-ipfs/ipfs /usr/local/bin/ipfs

Running the Program:
	Download the project files and place them in the Home Directory
	CD into the directory with the command in Terminal:
		$ cd ipfs_file_uploader
	Make sure Ganache is running in the background
	Compile and Migrate the smart contracts into the Blockchain with the following commands in Terminal:
		$ truffle compile --reset
		$ truffle migrate --reset
	Run the application with the following command in Terminal:
		$ sudo npm run start
	In Ganache go to the "Accounts tab" and copy the address under RPC Server
		This address is most likely: http://127.0.0.1:7545
		In Chrome click on the MetaMask Extension, login, and click on the button that says "Main Network"
			Select Custom RPC, and enter the address from the above step (http://127.0.0.1:7545)
	Now in Ganache on the "Accounts" tab, click on the key icon (Show Keys) next to any address and copy the private key
	Go back to the MetaMask Extension and click on the accounts button - the second to right icon on the top
		From that menu, select "Import Account" and paste the private key from the previous step
	In Google Chrome, go to the following address:
		localhost:3000
	Follow the instruction to upload the desired file, and then click "Submit"
	Wait about 10 seconds for the Metamask Notifications to arise and click on "Submit"
	The link to download the uploaded file is displayed at the bottom of the webpage
