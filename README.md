# hyperledger-fabric Version: 2.4.6 - Linux

install default fabric peers and docker images

curl -sSLO https://raw.githubusercontent.com/hyperledger/fabric/main/scripts/install-fabric.sh && chmod +x install-fabric.sh



# Alternative install microfab

# optional  check repo local machine ./microfab connect --force to regerate material, update git

docker pull ibmcom/ibp-microfab

docker run -d --name ibp-microfab -p 8080:8080 -p 9443:9443 ibmcom/ibp-microfab

docker ps

docker exec -it imageid  /bin/bash


# Set the MSP environment variables
git clone https://github.com/plucena/hyperledger-fabric

export CORE_PEER_ADDRESS=org1peer-api.127-0-0-1.nip.io:8080

export CORE_PEER_LOCALMSPID=Org1MSP

export CORE_PEER_MSPCONFIGPATH=/home/ibp-user/hyperledger-fabric/_mfcfg/Org1/org1admin/msp



# Run the queryinstalled command

peer lifecycle chaincode queryinstalled

# check peer chanels

peer channel list


# Deploy smart contracts 

cd hyperledger-fabric/chaincode

... follow the instrunctions from specific chaincode




