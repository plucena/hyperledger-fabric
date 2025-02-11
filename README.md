# hyperledger-fabric Version: 2.4.6

docker pull ibmcom/ibp-microfab

docker run -d --name ibp-microfab -p 8080:8080 -p 9443:9443 ibmcom/ibp-microfab

docker ps

docker exec -it <imageid>  /bin/bash


# Set the MSP environment variables
export CORE_PEER_LOCALMSPID=Org1MSP
export CORE_PEER_MSPCONFIGPATH=/opt/microfab/data/peer-org1/msp/

# Run the queryinstalled command
peer lifecycle chaincode queryinstalled

git clone https://github.com/plucena/hyperledger-fabric

cd hyperledger-fabric/chaincode

... follow the instrunctions from specific chaincode




