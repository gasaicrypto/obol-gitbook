# Create a DV With a Group

This quickstart guide will walk you through creating a Distributed Validator Cluster with a number of other node operators.

### Pre-requisites[​](https://docs.obol.org/next/run/start/quickstart_group#pre-requisites) <a href="#pre-requisites" id="pre-requisites"></a>

* A basic [knowledge](https://docs.ethstaker.cc/ethstaker-knowledge-base/) of Ethereum nodes and validators.
* A machine that meets the [minimum requirements](https://docs.obol.org/next/run/prepare/deployment-best-practices#hardware-specifications) for the network you intend to validate.
* If you are taking part using a [DappNode](https://dappnode.com/):
  * A computer with an up to date version of [DappNode](https://docs.dappnode.io/docs/user/install/overview/)'s software and an internet connection.
* If you are taking part using [Sedge](https://www.nethermind.io/sedge), or [Charon's Distributed Validator Node](https://github.com/ObolNetwork/lido-charon-distributed-validator-node) (CDVN) starter repo:
  * Ensure you have [git](https://git-scm.com/downloads) installed.
  * Ensure you have [docker](https://docs.docker.com/engine/install/) installed.
  * Make sure `docker` is running before executing the commands below.

### Step 1: Get your ENR <a href="#step-1-get-your-enr" id="step-1-get-your-enr"></a>

{% tabs %}
{% tab title="CDVN" %}
In order to prepare for a distributed key generation ceremony, you need to create an ENR for your Charon client. This ENR is a public/private key pair that allows the other Charon clients in the DKG to identify and connect to your node. If you are creating a cluster but not taking part as a node operator in it, you can skip this step.

```sh
# Clone the repo
git clone https://github.com/ObolNetwork/charon-distributed-validator-node.git
# Change directory
cd charon-distributed-validator-node/
# Use docker to create an ENR. Backup the file `.charon/charon-enr-private-key`.
docker run --rm -v "$(pwd):/opt/charon" obolnetwork/charon:v1.2.0 create enr
```

You should expect to see a console output like this:

```sh
Created ENR private key: .charon/charon-enr-private-key
enr:-JG4QGQpV4qYe32QFUAbY1UyGNtNcrVMip83cvJRhw1brMslPeyELIz3q6dsZ7GblVaCjL_8FKQhF6Syg-O_kIWztimGAYHY5EvPgmlkgnY0gmlwhH8AAAGJc2VjcDI1NmsxoQKzMe_GFPpSqtnYl-mJr8uZAUtmkqccsAx7ojGmFy-FY4N0Y3CCDhqDdWRwgg4u
```

{% hint style="danger" %}
Please make sure to create a backup of the private key at `.charon/charon-enr-private-key` Be careful not to commit it to git! **If you lose this file you won't be able to take part in the DKG ceremony nor start the DV cluster successfully.**
{% endhint %}

{% hint style="success" %}
If instead of being shown your `enr` you see an error saying `permission denied` then you may need to [update your docker permissions](https://docs.obol.org/next/adv/troubleshooting/errors#docker-permission-denied-error) to allow the command to run successfully.
{% endhint %}

For Step 2 of the quickstart:

* Select the **Creator** tab if you are coordinating the creation of the cluster (this role holds no position of privilege in the cluster, it only sets the initial terms of the cluster that the other operators agree to).
* Select the **Operator** tab if you are accepting an invitation to operate a node in a cluster, proposed by the cluster creator.
{% endtab %}

{% tab title="DappNode" %}


**Prepare an Execution and Consensus client**[**​**](https://docs.obol.org/next/run/start/quickstart_group#prepare-an-execution-and-consensus-client)

Before preparing the DappNode to take part in a Distributed Validator Cluster, you must ensure you have selected an execution client & consensus client on your DappNode under the 'Stakers' tab for the network you intend to validate.

1.  Login to the DappNode Interface:



    <figure><img src="https://docs.obol.org/img/dappnodeLogin.png" alt=""><figcaption></figcaption></figure>
2.  Click on the 'Stakers' tab on the left side, select an execution client (e.g. Geth) & consensus client (e.g. Lodestar) & click 'Apply changes'. This will start the syncing process which can take a number of hours.



    <figure><img src="https://docs.obol.org/img/SelectClients.png" alt=""><figcaption></figcaption></figure>
3.  Once the clients are finished syncing, it should reflect on your 'Dashboard' as shown below.



    <figure><img src="https://docs.obol.org/img/Dashboard.png" alt=""><figcaption></figcaption></figure>

**Install the Obol DappNode package**[**​**](https://docs.obol.org/next/run/start/quickstart_group#install-the-obol-dappnode-package)

With a fully synced Ethereum node now running on the DappNode, the below steps will walk through installing the Obol package via an IPFS hash and preparing for a Distributed Key Generation ceremony. Future versions of this guide will download the package from the official DappNode DappStore once a stable 1.0 release is made.

1. Before installing the package, make sure you are installing the correct one, this depends on which network your creator configures the cluster on, Holesky or Mainnet. You can find the link to both packages below:
   * [Holesky Repo](http://my.dappnode/installer/dnp/holesky-obol.dnp.dappnode.eth)
   * [Mainnet Repo](http://my.dappnode/installer/dnp/obol.dnp.dappnode.eth)
2.  Copy the latest IPFS hash from the release details dropdown.



    <figure><img src="https://docs.obol.org/img/DappnodeRepo.png" alt=""><figcaption></figcaption></figure>
3.  Go back to DappNode Dashboard > Dappstore, select the 'Public' tab, and accept the terms & conditions before proceeding.



    <figure><img src="https://docs.obol.org/img/PublicTab.png" alt=""><figcaption></figcaption></figure>
4.  Paste the IPFS hash you copied from Github and click 'Search' (It may take a minute for the package to be found.) You will then be presented with the package installation page. Under the blue 'Install' button, click on 'Advanced Options' & toggle the button to 'Bypass only signed safe restriction'.



    <figure><img src="https://docs.obol.org/img/BypassButton.png" alt=""><figcaption></figcaption></figure>
5.  Click 'Install' & in the config mode page > select new cluster & submit. (if you already have the config URL, you can select URL option.)



    <figure><img src="https://docs.obol.org/img/InstallPackage.png" alt=""><figcaption></figcaption></figure>
6.  Accept the terms & conditions and the install process will begin.



    <figure><img src="https://docs.obol.org/img/TermsAndConditions.png" alt=""><figcaption></figcaption></figure>

    <figure><img src="https://docs.obol.org/img/PackageInstalling.png" alt=""><figcaption></figcaption></figure>
7.  You should now be able to see the Holesky Obol package under the 'Packages' tab. Click on the package to see important details.



    <figure><img src="https://docs.obol.org/img/PackagesTab.png" alt=""><figcaption></figcaption></figure>
8.  Under the 'Info' tab, you will be see pre-generated ENRs, along with information such as the status of all five distributed validator clusters, their docker volumes & other menu options.



    <figure><img src="https://docs.obol.org/img/GetENR.png" alt=""><figcaption></figcaption></figure>
9. Select any of the ENRs listed that are not already in use. This ENR will be used in the next step.

For Step 2 of the quickstart:

* Select the **Creator** tab if you are coordinating the creation of the cluster (this role holds no position of privilege in the cluster, it only sets the initial terms of the cluster that the other operators agree to).
* Select the **Operator** tab if you are accepting an invitation to operate a node in a cluster, proposed by the cluster creator.
{% endtab %}

{% tab title="Sedge" %}

{% endtab %}
{% endtabs %}

### Step 2: Create a cluster or accept an invitation to a cluster <a href="#step-2-create-a-cluster-or-accept-an-invitation-to-a-cluster" id="step-2-create-a-cluster-or-accept-an-invitation-to-a-cluster"></a>

{% tabs %}
{% tab title="Creator" %}
### Collect addresses, configure the cluster, share the invitation

Before starting the cluster creation process, you will need to collect an Ethereum address for each operator in the cluster. They will need to be able to sign messages through MetaMask with this address. _(Broader wallet support will be added in future.)_ With these addresses in hand, go through the cluster creation flow.


{% endtab %}

{% tab title="Operator" %}
### Join the cluster prepared by the creator

Use the Launchpad or CLI to join the cluster configuration generated by the creator:
{% endtab %}
{% endtabs %}









