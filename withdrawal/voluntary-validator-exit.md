# Voluntary validator exit

{% stepper %}
{% step %}
### Chang folder chain config

* cd  into node folder

<figure><img src="../.gitbook/assets/Screenshot 2568-12-23 at 16.58.07.png" alt=""><figcaption></figcaption></figure>


{% endstep %}

{% step %}
### Publish voluntary exit for a validator

Run the lighthouse command to exit the validator (example):

{% code title="Publish voluntary exit" %}
```bash
docker compose run --rm -v $PWD/keys:/keys beacon lighthouse --testnet-dir=./config account validator exit --keystore=/keys/keystore-m_12381_3600_0_0_0-1766436756.json --beacon-node https://cl.cthscan.com
```
{% endcode %}

{% hint style="info" %}
The --keystore flag must point directly to the validator key .json file (the EIP-2335 voting keystore), not to the folder containing it.
{% endhint %}

* Enter your keystore password when prompted.
* When asked, type: Exit my validator

<figure><img src="../.gitbook/assets/Screenshot 2568-12-24 at 09.42.12.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Confirmation and next steps

On success you should see output similar to:

```bash
Successfully validated and published voluntary exit for validator 0xaaafec01dd02507e77b22a221eb99bd2c28b7caa54a578519a87ab89f011e0ddfb9564d09c68c7dc5d61be41620067a3
Voluntary exit has been accepted into the beacon chain, but not yet finalized. Finalization may take several minutes or longer. Before finalization there is a low probability that the exit may be reverted.
Current epoch: 1465, Exit epoch: 1470, Withdrawable epoch: 1726
Please keep your validator running till exit epoch
Exit epoch in approximately 1920 secs
```

* Your CTH will be withdrawn to your withdrawal address on epoch: 1726.
* Check validator status on: [https://beacon.changnodes.org](https://beacon.changnodes.org/)

![](<../.gitbook/assets/image (16)>)

Done!

In case your validator is active for less than 27 hours, you can not exit the validator for \
withfrawal.

{% code title="Example output" %}
```
Password is correct.

Validator 0xaaafec01dd02507e77b22a221eb99bd2c28b7caa54a578519a87ab89f011e0ddfb9564d09c68c7dc5d61be41620067a3 
is not eligible for exit. It will become eligible on epoch 1458
```
{% endcode %}
{% endstep %}
{% endstepper %}
