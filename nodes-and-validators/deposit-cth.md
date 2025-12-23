# Deposit CTH

Visit CTH Staking launchpad: [https://launchpad.changnodes.org](https://launchpad.changnodes.org/)

CTH Staking Launchpad

<figure><img src="../.gitbook/assets/Screenshot 2568-12-23 at 01.25.17.png" alt=""><figcaption></figcaption></figure>

{% stepper %}
{% step %}
### Open the Launchpad

Go to the launchpad: [https://launchpad.changnodes.org](https://launchpad.changnodes.org/) and click the "BECOME A VALIDATOR" button.
{% endstep %}

{% step %}
### Upload your deposit data

{% hint style="info" %}
Upload the deposit data file you generated. Choose the deposit\_data-\*.json file — do NOT upload a keystore file.
{% endhint %}

![](<../.gitbook/assets/image (1)>)

If the correct file is uploaded, you should see confirmation like this:

<figure><img src="../.gitbook/assets/Screenshot 2568-12-23 at 01.34.21.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Connect a wallet on CTH Network

When prompted, connect a wallet configured to use the CTH Network.

Recommended wallet: MetaMask.
{% endstep %}

{% step %}
### Choose an account with JBC tokens

<figure><img src="../.gitbook/assets/Screenshot 2568-12-23 at 01.37.44.png" alt=""><figcaption></figcaption></figure>

Select a wallet account that holds JBC tokens and connect it.

<figure><img src="../.gitbook/assets/Screenshot 2568-12-23 at 01.38.59.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/Screenshot 2568-12-23 at 01.40.27.png" alt=""><figcaption></figcaption></figure>

Once connected correctly, the UI should indicate your wallet is connected:

<figure><img src="../.gitbook/assets/Screenshot 2568-12-23 at 01.41.10.png" alt=""><figcaption></figcaption></figure>

Click the "CONTINUE" button.
{% endstep %}

{% step %}
### Review the summary

A summary page will be shown. Recheck your validator information and read/accept the risk.

<figure><img src="../.gitbook/assets/Screenshot 2568-12-23 at 01.42.48.png" alt=""><figcaption></figcaption></figure>

Click the "CONTINUE" button to proceed to deposit confirmation.
{% endstep %}

{% step %}
### Confirm deposit

Confirm the deposit details and proceed to submit the deposit.

<figure><img src="../.gitbook/assets/Screenshot 2568-12-23 at 01.44.10.png" alt=""><figcaption></figcaption></figure>

You will then confirm the transaction in your wallet.&#x20;

<figure><img src="../.gitbook/assets/Screenshot 2568-12-23 at 04.09.21.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Verify the deposit on the block explorer

Check your transaction on the CTH deposit contract: [https://cthscan.com/tx/0x96c58a90ec8da1dc7ba61eaa6928c772ad55f9fdb7e80ea1954b0facfb0e620e](https://cthscan.com/tx/0x96c58a90ec8da1dc7ba61eaa6928c772ad55f9fdb7e80ea1954b0facfb0e620e)

Verify the parameters — in particular your validator public key — are correct.

<figure><img src="../.gitbook/assets/Screenshot 2568-12-23 at 04.11.54.png" alt=""><figcaption></figcaption></figure>

Check your  deposit contract and Withdrawal Credential\
[https://beacon.changnodes.org/validators/deposits?v=included](https://beacon.changnodes.org/validators/deposits?v=included)

<figure><img src="../.gitbook/assets/Screenshot 2568-12-23 at 04.17.23.png" alt=""><figcaption></figcaption></figure>
{% endstep %}
{% endstepper %}
