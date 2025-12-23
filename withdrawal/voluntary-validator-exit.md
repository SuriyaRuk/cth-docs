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

<figure><img src="../.gitbook/assets/Screenshot 2568-12-23 at 17.05.59.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### Confirmation and next steps

On success you should see output similar to:

{% code title="Example output" %}
```
Password is correct.

Validator 0xaaafec01dd02507e77b22a221eb99bd2c28b7caa54a578519a87ab89f011e0ddfb9564d09c68c7dc5d61be41620067a3 
is not eligible for exit. It will become eligible on epoch 1458
```
{% endcode %}

* Your CTH will be withdrawn to your withdrawal address on epoch: 1458.
* Check validator status on: [https://beacon.changnodes.org](https://beacon.changnodes.org/)

![](<../.gitbook/assets/image (16)>)

Done!


{% endstep %}
{% endstepper %}
