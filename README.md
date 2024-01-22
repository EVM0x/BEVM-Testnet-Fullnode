

![Screenshot_17](https://github.com/uangdrop/BEVM-Testnet-Fullnode/assets/128940865/ac378bab-a3d9-4d87-bae9-2be374955516)

# BEVM-Testnet-Fullnode
<h1> Requirements </h1>
Machine :


* Storage space will increase as the network grows.
* Archive nodes may require a larger server, depending on the amount and frequency of data requested by a dApp.

| Component | Requirement |
| --- | --- |
| System | Ubuntu 20.04+ |
| CPU | 2 cores |
| Memory | 2 GB |
| SSD | 300 GB (recommended) |



<h1>  Installation </h1>

<b>Install docker on your VPS</b>


Update First 
```shell
sudo apt-get update
sudo apt-get upgrade
```
Download the installation shell of docker and Run
```shell
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```

Find a path
```shell
cd /var/lib
mkdir node_bevm_test_storage
```

Fetch the docker image
```shell
sudo docker pull btclayer2/bevm:v0.1.1
```

Run a docker container
```shell
sudo docker run -d -v /var/lib/node_bevm_test_storage:/root/.local/share/bevm btclayer2/bevm:v0.1.1 bevm "--chain=testnet" "--name=your_node_name" "--pruning=archive" --telemetry-url "wss://telemetry.bevm.io/submit 0"
```
<b> Note : If you want to get incentives from the BEVM TestNet FullNode Program, set "your_node_name" as Your BEVM address. </b>


Check it on the telemetry

Open https://telemetry.bevm.io/ to check your node state.
