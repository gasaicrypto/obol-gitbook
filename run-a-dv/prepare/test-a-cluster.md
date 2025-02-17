# Test a Cluster

Charon test commands are designed to help you evaluate the performance and readiness of your candidate cluster. It allows you to test your connection to other Charon peers, the performance of your beacon node(s), the readiness of your validator client, the performance of the MEV relays you will be using and the infrastructure on which you will run the cluster. It prints a performance report to the standard output (which can be omitted with the `--quiet` flag) and a machine-readable JSON format of the report if the `--output-json` flag is set.

{% tabs %}
{% tab title="Executable" %}
### Test all

Intended for running tests across all categories. Each flag should have a prefix for its category (i.e.: the flag `--endpoints` from the beacon tests becomes `--beacon-endpoints`). For details about each category refer to their respective sections.
{% endtab %}

{% tab title="Docker" %}
If you are running Charon using the [charon-distributed-validator-node repository](https://github.com/ObolNetwork/charon-distributed-validator-node/), services like the beacon node and validator client are hosted locally. To run the beacon node and validator client tests, you need to point them toward the correct Docker container, and also include the Docker container’s network. Check your docker networks with `docker network ls`. When you run the test command, specify the Docker network with `--network <name>`. Read more about docker networking [here](https://docs.docker.com/engine/network/).

### Test all

Intended for running tests across all categories. Each flag should have a prefix for its category (i.e.: the flag `--endpoints` from the beacon tests becomes `--beacon-endpoints`). For details about each category refer to their respective sections.
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Regular Test" %}

{% endtab %}

{% tab title="Load Test" %}

{% endtab %}
{% endtabs %}



