# Voluntary validator exit

{% stepper %}
{% step %}
### Download the Lighthouse binary

Download the lighthouse binary from https://github.com/sigp/lighthouse/releases

![](<../.gitbook/assets/image (4)>)

Choose the binary matching your architecture.
{% endstep %}

{% step %}
### Download via command line

* Copy the link address for the chosen release asset.

![](<../.gitbook/assets/image (6)>)

* Open the `deposit-cli` folder and run (example):

{% code title="Download example" %}
```
wget https://github.com/sigp/lighthouse/releases/download/v4.5.0/lighthouse-v4.5.0-x86_64-apple-darwin-portable.tar.gz
```
{% endcode %}
{% endstep %}

{% step %}
### Extract the archive

* Extract the tar.gz file:

{% code title="Extract" %}
```
tar -zxvf <tar.gz file>
```
{% endcode %}

![](<../.gitbook/assets/image (8)>)

* Test the binary:

{% code title="Test binary" %}
```
./lighthouse
```
{% endcode %}

![](<../.gitbook/assets/image (10)>)
{% endstep %}

{% step %}
### Clone chain config

* Clone the chain config repository into a local folder named `config`:

{% code title="Clone config" %}
```
git clone https://github.com/jibchain-net/node.git -b config config
```
{% endcode %}

![](<../.gitbook/assets/image (12)>)
{% endstep %}

{% step %}
### Publish voluntary exit for a validator

Run the lighthouse command to exit the validator (example):

{% code title="Publish voluntary exit" %}
```
./lighthouse --testnet-dir=./config account validator exit --keystore=./validator_keys-test/validator_keys/keystore-m_12381_3600_0_0_0-1701319485.json --beacon-node https://metrabyte-cl.jibchain.net/
```
{% endcode %}

{% hint style="info" %}
The --keystore flag must point directly to the validator key .json file (the EIP-2335 voting keystore), not to the folder containing it.
{% endhint %}

* Enter your keystore password when prompted.
* When asked, type: Exit my validator

![](<../.gitbook/assets/image (14)>)
{% endstep %}

{% step %}
### Confirmation and next steps

On success you should see output similar to:

{% code title="Example output" %}
```
Successfully validated and published voluntary exit for validator 0x8debdde83a995937ec83ba8cd9b653c9e28e5405b90d9503389032234201e61fe451900f5b95bab3789556f46568348b
Voluntary exit has been accepted into the beacon chain, but not yet finalized. Finalization may take several minutes or longer. Before finalization there is a low probability that the exit may be reverted.
Current epoch: 4152, Exit epoch: 4157, Withdrawable epoch: 4413
Please keep your validator running till exit epoch
Exit epoch in approximately 1920 secs
```
{% endcode %}

* Your JBC will be withdrawn to your withdrawal address on epoch: 4413.
* Check validator status on: https://dora.jibchain.net

![](<../.gitbook/assets/image (16)>)

Done!
{% endstep %}
{% endstepper %}
