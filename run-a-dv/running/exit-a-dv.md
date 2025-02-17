# Exit a DV

### Introduction[​](https://docs.obol.org/next/run/running/quickstart-exit#introduction) <a href="#introduction" id="introduction"></a>

Users looking to exit staking entirely and withdraw their full balance back must sign and broadcast a "voluntary exit" message with validator keys which will start the process of exiting from staking. In the case of a DV, Charon nodes need to broadcast a partial exit to the other nodes of the cluster. Once a threshold of partial exits has been received by any node, the full voluntary exit will be sent to the beacon chain. This process will take 27 hours or longer depending on the current length of the exit queue. Once the validator is exited, the principal plus unclaimed rewards will go to the withdrawal address of the validator. Depending on the cluster's withdrawal configuration, users can claim their proporiton of principal and rewards.

There are two ways to sign the partial exit and broadcast the full exit. Both the solutions don't require gas.

1. **Using the Charon’s exit solution** - It is an Obol hosted solution which is facilitated by Obol APIs. It provides several benefits such as signing partial exits for multiple validators at once, live monitoring of partial exits status via launchpad and ability to download partial exits and broadcast them later as required. Users don’t have to worry about the intricacies of validator clients. Charon Exit abstracts all the complexity.
2. **Using the Validator Clients directly** - Users can also directly use the validator client that is connected to your Charon client to submit partial exits, as the client only signs a partial exit message using its share of the private key. Charon will combine the partial exit messages from the other operators. Once the threshold is reached, they are submitted to the beacon node. All of this is usually wrapped under a single command and hence users cannot download full exit signatures for broadcasting it later. In this case, users cannot use launchpad to monitor exit status and will have to use grafana to query the partial exit status.

{% hint style="info" %}
* A threshold of operators need to run the exit command for the exit to succeed. This is the same threshold as is specified during cluster creation.
* **Ensure that all operators within a cluster consistently use either the hosted solution (Charon Exit) or the non-hosted solution (Validator Client Exit). Mixing both solutions within the same cluster—where some operators use Charon Exit while others use Validator Client Exit—is not allowed.**
* In case of validator client native exits, partial exits can be broadcast by any validator client as long as the threshold for the cluster is reached.
* If a Charon client restarts after the exit command is run but before the threshold is reached, it will lose the partial exits it has received from the other nodes. If all Charon clients restart and thus all partial exits are lost before the required threshold of exit messages are received, operators will have to rebroadcast their partial exit messages.
* All operators need to use the same `EXIT_EPOCH` for the exit to be successful. Assuming you want to exit as soon as possible, the default epochs included in the below commands should be sufficient for the respective network.
{% endhint %}

As per your preferences, choose the correct combination of -

1. **Network** : Mainnet or Holesky
2. **Exit Type** : Hosted (Charon) or Non-hosted (Validator client)
3. **Validator Quanity**: Exit single or Exit all validators
