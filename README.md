# Masternode Setup Guide - MANUALLY GUIDE

### Required:

1. MNsavings for Collateral 

2. Download Local Wallet for your operating system: : https://github.com/mnsccoin/src/releases

3. You will need also VPS with Ubuntu 18.04

**VPS WALLET:**

1. After you longin on your VPS , with this command you will download masternode-installer.   
`wget https://raw.githubusercontent.com/mnsccoin/src/master/masternode-install-ubuntu-18.04.sh`  
 

2. With this command you will make masternode-install.sh executable:  

- Use this: <br>
`sudo chmod +x masternode-install-ubuntu-18.04.sh` <br>

3. Now install your masternode.  
`./masternode-install-ubuntu-18.04.sh`

4. Press ENTER when the system ask for Masternodekey to create one automatically! 


or  go to your **LOCAL WALLET:**
Open your wallet and wait until your wallet has downloaded the blockchain.

Go to “Tools”.
Click “Debug console”.
This is the console where you will execute all commands.

Create a new masternode private key.

```
createmasternodekey
```

Example output

7VatfYVk5fFMTymPDhgSURAESDACJhWpd89WHGoh35d9fbLQPj5


Send the collateral


Show your collateral address.
```
getaccountaddress "MN1"
```

Example output
```
MDC99hZmSmYEcBu4WcxA2TCT6KBqHB6Hos
```
Transfer the required amount of coins to the “collateral address” that you created using the command “getaccountaddress "MN1"”.

Wait until the transaction has the required masternode confirmations.

Go to “Tools”.
Click “Debug console”.
Enter the following command.
```
getmasternodeoutputs
```

Example output

```
[
  {
    "txhash": "506a242ccbfd2555bcd9cff5f4041752c911f39cb2905acc83ccfe0cf8808df9",
    "outputidx": 1
  }
]
```

Modify the following line in your masternode.conf file and paste it into:
```
MN1 VPSIP:22878 7VatfYVk5fFMTymPDhgSURAESDACJhWpd89WHGoh35d9fbLQPj5 506a242ccbfd2555bcd9cff5f4041752c911f39cb2905acc83ccfe0cf8808df9 1
```
MN1 - Alias for your masternode.

VPSIP- External IP address of your VPS.

5727 - The port for MNSC

7VatfYVk5fFMTymPDhgSURAESDACJhWpd89WHGoh35d9fbLQPj5 - Masternode private key from the command “createmasternodekey”.

506a242ccbfd2555bcd9cff5f4041752c911f39cb2905acc83ccfe0cf8808df9 - Value “txhash” from the command “getmasternodeoutputs”.

1 - Value “outputidx” from the command “getmasternodeoutputs”.


Save the file and close.

Close your wallet.

Restart your wallet! 
On Masternode tab in your wallet - Start the masternode! 

If you still facing any issues 
then join our <a href="https://discord.gg/PW77729pAq"> Discord server</a> for support. 
or join our Telegram chat <a href="https://t.me/+CKQ2LJw3t3U1MGIx"> Telegram Chat</a> !
We are happy to help you there! 
