# Updated to Fabric 2.x
#1. Docker file for setting up the Orderer
# FROM hyperledger/fabric-orderer:1.4.2
FROM hyperledger/fabric-orderer:2.1

LABEL  maintainer="Helio Pesanhane <pesanhane@gmail.com>"

#2. Create the folder for configurations
RUN mkdir -p /var/hyperledger/config

#3. Copy the crypto for orderer
#COPY ./fabric-ca/client/orderer/orderer/msp  /var/hyperledger/orderer.smallfarmer1.com
COPY ./config/crypto-config/ordererOrganizations/smallfarmer1.com/orderers/orderer.smallfarmer1.com /var/hyperledger/orderer.smallfarmer1.com

#4. Copy the genesis file
COPY ./config/orderer/agrifoodgenesis.block  /var/hyperledger/config/agrifoodgenesis.block

#5. Copy the orderer YAML
COPY ./config/orderer/orderer.yaml /var/hyperledger/config/orderer.yaml

#6. Launch the Orderer
CMD orderer
