# create package

npm init -y

npm install fabric-contract-api fabric-shim

npm install --save-dev typescript @types/node

npx tsc --init

peer lifecycle chaincode package productChaincode.tar.gz --path ./ --lang node --label productChaincode_1.0


# install package




# interact with package

Create a Product:
peer chaincode invoke -C mychannel -n productChaincode -c '{"Args":["CreateProduct", "1", "Product 1", "100"]}'


Read a Product:
peer chaincode query -C mychannel -n productChaincode -c '{"Args":["ReadProduct", "1"]}'

Update a Product:

peer chaincode invoke -C mychannel -n productChaincode -c '{"Args":["UpdateProduct", "1", "Updated Product 1", "150"]}'
Delete a Product:

peer chaincode invoke -C mychannel -n productChaincode -c '{"Args":["DeleteProduct", "1"]}'

Get All Products:
peer chaincode query -C mychannel -n productChaincode -c '{"Args":["GetAllProducts"]}'
