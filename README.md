# [Guide] How to Mine Testnet4 Bitcoin 

## Background
I wanted to test my NerdAxe and Avalon Nano3S hashers on something that had a much higher likelihood of hitting a block than Bitcoin so I chose to try to mine some Testnet BTC. The Testnet BTC network only has about 1.4 PH/s of hashpower and a network difficulty of 630M (at the time of this writing) so that meant that my little NerdAxe and Nano3S with their 1.3 TH/s and 6 TH/s actually has a chance of finding a block. 

However, I could not find any guides online for how to mine on Testnet with my Umbrel node. After fumbling around I finally got it to work and figured I'd write up what worked for me so that maybe it can help others.

## What you will need
- A SHA256 hasher (i.e. Nerdaxe, Bitaxe, Avalon Nano3S, or any other Bitcoin miner)
- A computer where you can run the following software (in my case I'm running this on a Raspberry Pi 4 with Umbrel):
  - Bitcoin Knots or Bitcoin Core
  - Public Pool app 
- Sparrow Wallet app running on a computer. Doesn't have to be on the same computer that's running Bitcoin Knots/Core as it will only be used to generate a testnet wallet receive address.

## Procedure

### Create Testnet4 Wallet and Receive Address
In order to mine tesnet BTC, you will need a valid testnet BTC address. Testnet BTC addresses start with `tb1q...`. In order to get a valid testnet address, we'll use Sparrow Wallet.

1. Download and install Sparrow Wallet
2. The simplest way to start Sparrow using testnet is via the Tools > Restart in Testnet menu command. This will close Sparrow, and restart it with a separate testnet configuration in the testnet folder in Sparrow home. You can also start Sparrow in tesnet mode using the terminal:
    - macOS: `open /Applications/Sparrow.app --args -n testnet4`
    - Linux: `Sparrow/bin/Sparrow -n testnet4`
    - Windows: `Sparrow.exe -n testnet4`
3. You should notice text at the top right that says "testnet4" when you open Sparrow
4. Create a software or hardware wallet in Sparrow
5. Click on Receive to get an address. A valid testnet BTC address should start with `tb1q...`

### Install Bitcoin Node Software
We need Bitcoin node software running on the testnet4 network so that we can point our Public Pool instance to it. You can use Bitcoin Knots, Bitcoin Core, or any other node software that lets you switch the network to testnet4.

1. Install Bitcoin Knots
2. Go to Settings > Network Selection and switch it from `Mainnet` to `Testnet4`
<img width="1582" height="1625" alt="image" src="https://github.com/user-attachments/assets/29b92563-9133-4abe-950b-2f5631cfa1de" />

3. Wait for the initial blockchain download to complete. Since this is testnet, it shouldn't take as long as the mainnet blockchain since it's only ~60GB.

### Install Public Pool App
You can use other apps as well such as Bassin but they may have different ways to configure them to work with testnet. In this guide, I will focus on what I used and got working which is Public Pool. In Umbrel, you can find Public Pool in the app store. 

1. Download Public Pool app
2. Once it's done downloading, if it started automatically, right click on its icon and click "Stop" to stop it.
3. Open the File app in Umbrel and go to Apps > Public Pool and open `docker-compose.yml`.
4. Change the `network` value from `mainnet` to `testnet` (NOT `testnet4`)
<img width="2116" height="1249" alt="image" src="https://github.com/user-attachments/assets/c5984ba9-a0fe-4fff-bd3e-a8c9e0966f2b" />

