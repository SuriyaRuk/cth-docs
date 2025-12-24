# Set new withdrawal credential

For a validator key that was not generated with a `--eth1_withdrawal_address` set.

{% stepper %}
{% step %}
### 1. Open your deposit-cli folder

Open the `deposit-cli` folder that you used to generate validator keys.

The folder should contain your generated keys (for example `validator_keys`).

<figure><img src="../.gitbook/assets/Screenshot 2568-12-23 at 14.43.57.png" alt=""><figcaption></figcaption></figure>
{% endstep %}

{% step %}
### 2. Generate BLS-to-execution-change

From inside the `deposit-cli` folder run:

{% code title="generate bls-to-execution-change" %}
```bash
./deposit.sh --language english  generate-bls-to-execution-change --chain=cth
```
{% endcode %}

You will be guided through interactive prompts:

* Enter your mnemonic (space-separated).
  * Example mnemonic: worry uncover treat tonight input soon worth code benefit hotel hungry stamp subway neck join trap flat music argue air menu quantum volcano connect
* Enter the index position for the keys to start generating withdrawal credentials (e.g., `0`).
* Enter a list of the validator index number(s) of your validator(s) as identified on the beacon chain (separate multiple with spaces or commas).
  * Check your validator indices on: [https://beacon.changnodes.org](https://beacon.changnodes.org/)
  * Examples: `500` (1 validator) or `500, 501, 502` (3 validators).
* Enter a list of the old BLS withdrawal credentials of your validator(s).
  * Open the `deposit-data.json` file and copy the old withdrawal credential(s).
  * Old withdrawal credentials start with `00`.
  * Example: 0098b66b3d28ae0694d1c25e58d0636c3e2a0fe306e57d067aae98de2171820f

![](<../.gitbook/assets/image (21)>)
{% endstep %}

{% step %}
### 3. Provide the new execution (withdrawal) address

* Enter the 20-byte execution address for the new withdrawal credentials (this is your wallet address).
  * Example: `0x53D1644eExxxxxxxxxxxxxxx3f99B90bf34b93`
* Repeat the execution address to confirm.

Important:

{% hint style="warning" %}
You CANNOT change the execution (withdrawal) address once it has been set on-chain. Ensure you control the address before confirming.
{% endhint %}

On success, the tool will produce SignedBLSToExecutionChange JSON files in:

```
deposit-cli/bls_to_execution_changes
```

Check the generated files:

{% code title="List generated files" %}
```bash
ls ./bls_to_execution_changes
```
{% endcode %}

![](<../.gitbook/assets/image (22)>)
{% endstep %}

{% step %}
### 4. Broadcast the BLS-to-execution-change to your consensus client

Use Docker to broadcast the signatures to the consensus client. From the `deposit-cli` folder (ensure `./bls_to_execution_changes` exists and contains the JSON files):

{% code title="Broadcast with prysmctl" %}
```bash
docker run -ti -v ./bls_to_execution_changes:/bls_dir gcr.io/prysmaticlabs/prysm/cmd/prysmctl:latest validator withdraw -beacon-node-host=https://cl.cthscan.com --path=/bls_dir --accept-terms-of-use --confirm
```
{% endcode %}

After the command completes, your BLS-to-execution-change should be submitted to the network.
{% endstep %}
{% endstepper %}

Done!
