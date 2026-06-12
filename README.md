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
   - 
