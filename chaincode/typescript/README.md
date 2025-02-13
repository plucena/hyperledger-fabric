# create package

npm init -y

npm install fabric-contract-api fabric-shim

npm install --save-dev typescript @types/node

npx tsc --init

peer lifecycle chaincode package productChaincode.tar.gz --path ./ --lang node --label productChaincode_1.0


# install package

peer lifecycle chaincode install productChaincode.tar.gz 


# Approve the chaincode definition

peer lifecycle chaincode approveformyorg \
    --channelID channel1 \
    --name productChaincode \
    --version 1.0 \
    --sequence 1 \
    --signature-policy "OR('SampleOrg.admin')"

# Commit the Chaincode Definition

peer lifecycle chaincode commit \
  --channelID channel1 \
  --name productChaincode \
  --version 1.0 \
  --sequence 1 \
  --signature-policy "OR('SampleOrg.admin')"
  
# interact with package

Create a Product:
peer chaincode invoke -C mychannel -n productChaincode -c '{"Args":["CreateProduct", "1", "Product 1", "100"]}'


Read a Product:
peer chaincode query -C mychannel -n productChaincode -c '{"Args":["ReadProduct", "1"]}'

Update a Product:

peer chaincode invoke -C mychannel -n productChaincode -c '{"Args":["UpdateProduct", "1", "Updated Product 1", "150"]}'
Delete a Product:

Delete a product:

peer chaincode invoke -C mychannel -n productChaincode -c '{"Args":["DeleteProduct", "1"]}'

Get All Products:
peer chaincode query -C channel1 -n productChaincode -c '{"Args":["GetAllProducts"]}'
