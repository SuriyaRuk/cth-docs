# Generate Validator Keys

### Installation Tool

```bash
git clone https://github.com/Chang-Chain/staking-deposit-cli.git
```

<figure><img src="../.gitbook/assets/Screenshot 2568-12-22 at 15.33.31.png" alt=""><figcaption></figcaption></figure>

```bash
cd staking-deposit-cli
```

<figure><img src="../.gitbook/assets/Screenshot 2568-12-22 at 15.37.46.png" alt=""><figcaption></figcaption></figure>

```bash
./deposit.sh install
```

<figure><img src="../.gitbook/assets/Screenshot 2568-12-22 at 15.39.50.png" alt=""><figcaption></figcaption></figure>

### Generate Validtor Keys

{% stepper %}
{% step %}
### Create key and `deposit_data-*.json`

```bash
mkdir validator_keys
```

```bash
./deposit.sh --language english new-mnemonic --num_validators=<NUM_VALIDATORS> --mnemonic_language=english --chain=cth --eth1_withdrawal_address=<withdraw_address> --folder=validator_keys
```

Example:

```bash
./deposit.sh --language english new-mnemonic --num_validators=1 --mnemonic_language=english --chain=cth --eth1_withdrawal_address=<change-to-your-address> --folder=validator_keys
```
{% endstep %}

{% step %}
### Confirm withdrawal address And Create your password and confirm your password

When you run the tool you'll see prompts similar to:

```
***Using the tool on an offline and secure device is highly recommended to keep your mnemonic safe.***


**[Warning] you are setting an Eth1 address as your withdrawal address. Please ensure that you have control over this address.**

Repeat your execution address for confirmation.: <change-to-your-address>
```

```
Running deposit-cli...

***Using the tool on an offline and secure device is highly recommended to keep your mnemonic safe.***

Please choose your language ['1. العربية', '2. ελληνικά', '3. English', '4. Français', '5. Bahasa melayu', '6. Italiano', '7. 日本語', '8. 한국어', '9. Português do Brasil', '10. român', '11. Türkçe', '12. 简体中文']:  [English]:
Create a password that secures your validator keystore(s). You will need to re-enter this to decrypt them when you setup your Ethereum validators.:
Repeat your keystore password for confirmation:
```
{% endstep %}

{% step %}
### Remember your mnemonic key

The tool will display your mnemonic (seed phrase). Write it down and store it safely. It is the ONLY way to retrieve your deposit.

Example output:

```
This is your mnemonic (seed phrase). Write it down and store it safely. It is the ONLY way to retrieve your deposit.


enact roast unfold opera diamond argue trigger drip rough bicycle unhappy direct true security rack original fine make road select food peace ranch junior


Press any key when you have written down your mnemonic.
```
{% endstep %}

{% step %}
### Put your mnemonic key to verify that you saved it

You will be asked to re-enter the mnemonic to confirm you recorded it. You may enter only the first 4 letters of each word if you prefer.

Example:

```
Please type your mnemonic (separated by spaces) to confirm you have written it down. Note: you only need to enter the first 4 letters of each word if you'd prefer.

: enact roast unfold opera diamond argue trigger drip rough bicycle unhappy direct true security rack original fine make road select food peace ranch junior
```
{% endstep %}

{% step %}
### Waiting for generate key

The tool will generate the keys and show progress. Example output:

```
                  #####     #####
                ##     #####     ##
    ###         ##   #######     #########################
    ##  ##      #####               ##                   ##
    ##     #####                 ##                       ##
    ##     ##                     ##                      ###
   ########                        ##                     ####
   ##        ##   ###         #####                       #####
   #                          ##                         # #####
   #                            #                        #  #####
   ##                             ##                    ##
   ##                              ##                   ##
   ##             ###              ##                   ##
   ###############                 ##                   ##
   ###               ##                                 ##
      #############################                    ##
                     ##                             ###
                     #######     #################     ###
                     ##   ## ##        ##   ##    ###
                     ##############          #############

Creating your keys.
Creating your keystores:	  [####################################]  1/1

Success!
Your keys can be found at: validator_keys/validator_keys

Press any key.
```
{% endstep %}

{% step %}
### Your keys can be found at: `validator_keys-test/validator_keys`

List the directory:

```bash
ls -la validator_keys/validator_keys
```

Example output:

```
total 16
drwxr-xr-x  4 user  staff  128 Dec  3 15:14 .
drwxr-xr-x  3 user  staff   96 Dec  3 15:14 ..
-r--r-----  1 user  staff  702 Dec  3 15:14 deposit_data-1701591267.json
-r--r-----  1 user  staff  710 Dec  3 15:14 keystore-m_12381_3600_0_0_0-1701591267.json
```

{% hint style="info" %}
If you input --num\_validators greater than 1, the list of files will show multiple `keystore-m_...` files equal to the number of validators requested.
{% endhint %}
{% endstep %}
{% endstepper %}
