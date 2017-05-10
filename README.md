# Amply-Trustlab

<img src="https://cloud.githubusercontent.com/assets/25197053/24645519/bbfcedd0-1918-11e7-9763-a42d9d4935c5.jpg" alt="Amply Logo" width="150" height="150">

Amply is a digital protocol for scaling the impacts of health, education and other socio-economic development investments through decentralised networks through decentralised networks. Amply captures and verifies data to prove service delivery, value transfers and outcomes in transparent and accountable ways. This uses Blockchain and other decentralised Web 3.0 technologies. This increases trust, decreases administrative costs, reduces benefit fraud and provides richer data to demonstrate service performance and outcomes.

## Purpose

Amply vision is to have a completely open,decentralised,autonomous social benefit platform that can underpin a range of services and funding model. This will increase trust, decrease administrative costs, reduce benefit fraud and provide richer data to demonstrate service performance and outcomes.

## Contents

:warning: **WORK IN PROGRESS** |
:star: **COMING SOON**

Not all of the below is yet fully implemented.

### ecd-rn / Mobile application 

* [ecd-rn](https://github.com/TrustlabTech/ecd-rn/blob/master/README.md)
* Always up-to-date [React Native](https://facebook.github.io/react-native/) 
* Mobile application working without Blockchain component.
* :warning: Cryptography
* :warning:	Verifiable Claim
* :warning:	Populate Template from bot
* :warning: Add meta data
* :warning: Hash + Signature

### ecd-platform (PHP laverval) / front-end development 

* [ecd-platform](https://github.com/TrustlabTech/ecd-platform/blob/master/readme.md)
* always up-to-date [PHP laverval](https://laravel.com/docs/5.4)
* CRUD data from database

### Service Assurance Bot 

* Fetch Verifiable Claims
* Process Verifiable Claims
* Sign & Hash Verifiable Claims
* Fetch Verification Data: Verified Registry Database,Interact with Attendance Smart Contract,Verify Verifiable Claims         Metadata
* Service Verification Algorithm

### Ethereum Smart Contract

* Always up-to-date [Solidity](https://solidity.readthedocs.io/en/develop/)
* :warning: Smart contract - Cryptographic currency(AMPS)
* :warning: Smart contract - Attendance
* :star: Dashboard for smart contracts

## modules

## Identity Registry Module

Each participant in the Amply ECD system must obtain a self-sovereign Decentralised Digital Identity (DID). DIDs are created for children, service providers and ECD centres. A DID comprises a universally unique identification number that is registered on the Blockchain using the Consent Protocol Ethereum Identity Service (EIS) Dapp .The DIDs is stored in the Ethereum Identity Service (EIS) and also in the traditional RDBMS back-end.The RDBMS back-end is a Reliable public registry of children, caregivers and ECD agents will be available to planners, funders, researchers and service providers. This will not duplicate or fraudulent identities. The Identities will be searchable on the Ethereum Blockchain, together with a URL pointer to the encrypted identity Data Repository Index record for each identity. This will demonstrate a real-world implementation of the new Self-Sovereign Distributed Digital Identity architecture that is being developed through W3C & the Rebooting the Web of Trust workshops.The Ledgered records extracted from the Ethereum Blockchain will provide lists of registered identities.

## Service Delivery Claims Module

The Amply Service Delivery Claims Module enables form-based data to be captured and submitted using the Amply Mobile Application (for instance, an attendance form), to replace paper-based data capture. This data are compiled into a Verifiable Claim format that is cryptographically signed by the service provider submitting the claim through the Mobile Application. This creates accountability for the attendance claim and generates a digital record that cannot be repudiated or changed. Verifiable Claims are based on a cutting-edge technical specification developed by the Verifiable Claims Working Group of the Web 3 Consortium that is defining standards for the decentralised ‘Web of Trust’. 
Attendance Claim data includes the identifier of the service-provider and practitioner, the nature of the service, date and time, identifiers of the beneficiaries (children) and other relevant information. A cryptographic hash is generated from the verifiable claim, which is a unique fingerprint of the data. The hash of the verifiable claim could be considered a digital asset, as this represents the authenticity and proof of a claim.

Security and verification metadata such as the GPS location are also captured by the mobile application, which is used to validate the claim. On submission of a claim, the Mobile Application triggers a transaction in the Blockchain using the Ethereum Smart Contract AMP Token-generator DApp, into which it inserts the hash of the verifiable claim. The claim data are encrypted and transmitted to the ECD Enterprise Staging Server. (In future, claim data will be submitted directly to each ECD Centre’s Organisational Data Store, from where it will only be accessible with the consent of the ECD Centre controller).

Cryptographic Tokens can be designed to represent value on a Blockchain. In the Amply system, we call these tokens AMPs. One AMP represents one service unit claim (for instance the claim by a service provider that ‘I delivered an early learning service to one child’). Each token is recorded together with a cryptographic hash of its metadata - including the service provider’s DID, time, location, beneficiary DIDs and type of service delivered. This means that data associated with a claim cannot be repudiated or defrauded. We have designed the data specification for an Ethereum Smart Contract token generator DApp that automatically issues AMPs to an ECD centre’s wallet when a transaction is initiated by the Amply Mobile App. This transaction is triggered by a registered ECD service provider digitally signing an attendance claim using the app. AMPs are however only released to the ECD Centre’s wallet once the service verification bot validated the service delivery claim.

The Ethereum Smart Contract AMP Token-Generator DApp can function independently of any third-party, so the transactional record-keeping of ECD services could become somewhat autonomous. Note that this module does not verify the claim, but simply records the transaction. Service Verification Bot verifies the claim details independently and references the Blockchain transaction for proof of the transaction and to confirm the integrity of the data against the recorded hash.

The encrypted claim data is sent from the Amply Mobile Application via the ECD API to be stored in the ECD Enterprise Staging Server database. During Q2 2017 the technical specifications for this module will be finalised and the first Proof of Concept Ethereum Smart Contract AMP Token-generator DApp will be developed and tested. The Amply Mobile Application will be updated to directly generate Verifiable Claims and to initiate AMP transactions to the Blockchain. The code will be published in a public Github repository for peer review and community collaboration and development.

During Q3 Blockchain Wallet features will be included in the Amply Mobile App, which will enable the ECD centre to view their AMPs balance and transaction history. Authorised account-holders will be able to exchange AMPs for cash transfer payments or other value exchanges through the Amply Decentralised Exchange DApp which will be designed and developed during Q3/Q4 2017, using their mobile app.

## Service Provider Wallet Manager Module	

Each ECD centre will be registered with a Decentralised IDentity on the Ethereum Blockchain. This simultaneously creates a ‘wallet’ address to which tokens can be sent. Securing this Service Provider Wallet requires management of the cryptographic keys that are used to sign Blockchain transactions. We hope to integrate wallet management capabilities into the Amply Mobile Application during Q3 / Q4 2017. This will require further research and development.

## Attendance Smart Oracle Module

After an attendance claim has been submitted using the mobile app, this must be independently verified. The Amply Service Verification Bot is a software agent that processes the information it receives and check that this meets the criteria for verifying a claim. For instance, this systematically checks that all the identifiers in a claim are valid and have not been duplicated. It references the Blockchain transaction that was created and checks that the data received matches the hash of the verifiable claim in the transaction record. This agent also takes in the security metadata that was sent by the mobile app and checks this against expected parameters such as matching the GPS location where the attendance record was taken with the GPS location of the ECD centre.
 
Once all the required checks have been passed, the Service Verification Bot digitally signs the claim to verify that it is valid and this automatically allows related exchange transactions on the Blockchain to proceed which will accept or reject the release of AMP tokens. If a claim is rejected by the Service Verification Bot, it produces reason codes that can be viewed through an administration interface.

Initially the Service Verification Bot will be executed within a cloud-based software container. In future we anticipate that Service Verification Bot will execute within a trusted execution environment (e.g. Intel SGX), where the cryptographic keys belonging to the Service Verification Bot would be stored within a protected hardware enclave within the microchip that is executing the code. We are collaborating with Microsoft Azure to test this new functionality as it becomes available.

During Q2 2017 we will be defining the technical specifications for the data inputs and outputs of the Service Verification Bot and developing prototype code to execute a proof of concept of the oracle mechanism. During Q3Q4 2017 we expect to integrate the Service Verification Bot into the Decentralised Exchange mechanism and to demonstrate exchange transactions taking place automatically.

## Decentralised AMPs Exchange Module

AMPs should be exchangeable for any other value token - including mainstream cryptocurrencies. This should enable configuration of Amply to meet the needs of virtually any model of social benefit delivery. For instance, AMPs could equally be exchanged for digital vouchers that can be used to purchase a specific category of goods from a nominated supplier, or they could be exchanged for (manual or automated - in future) cash transfers.

The Decentralised Exchange is an Ethereum DApp that enables anyone to offer a cryptographic token, digital vouchers or fiat currency in exchange for AMPs.  For an exchange transaction to complete requires that the transaction must be signed by the Service Verification Bot. In simple terms, this matches the hash of the verifiable claims within the transaction that was created at the time of a service provider submitting their claim to the Service Verification Bot.

During Q2 2107 we will be reviewing candidate open-source reference code examples of decentralised exchange DApps and writing the technical specifications for the Amply Decentralised Exchange DApp.

In Q3 2017 a proof of concept DApp will be developed and tested. The Github repository for this will be public by the end of Q3 2017 for peer review. By the end of Q3 2017 we expect to release the beta version of the Decentralised Exchange DApp, with production release scheduled for Q4 2017. However this can only happen after a formal independent security audit has been undertaken on the DApp code, which will be contingent on the availability of funding.

## Analytics Module

Service delivery transactions recorded on the Blockchain will be viewed using a web application blockchain explorer. This will provide real-time information, such as an indication of the number of children receiving ECD services, based on claims submitted through the Amply Mobile App. During Q2 2017 the technical requirements for this application will be specified. The web application will be built during Q3 2017, adapting an existing open-source Ethereum Blockchain Explorer application for this purpose. We will initially only be able to demonstrate transactions taking place through the Ethereum Smart Contract AMP Token-generator DApp. Once the Decentralised AMPs Exchange DApp becomes operational in Q3 / Q4 2017, exchange transactions will be included on the dashboard.

## ECD Enterprise Database Server 

The ECD Enterprise Database Server is needed as we do not want to store personal information on the Ethereum blockchain, as it is public and not privacy preserving. We are therefore going to store the information in the enterprise database server. The DIDs will be stored on a private ethereum blockchain that will be monitored by Amply.

## Mobile Application

The Amply Mobile application will be further developed during Q2 2017 to enable compiling and processing of verifiable claims with cryptographic signatures and perform other hashing and encryption processes. In Q3 2017 the mobile app will require an Ethereum light wallet (using available open-source code) to enable the App to communicate directly with the Ethereum Blockchain for initiating transactions in the Ethereum Smart Contract AMP Token-generator DApp which will allow ECD centres to receive and send AMP tokens. Version 2.0 Beta of the Amply Mobile App is planned for release at the end of May 2017.

## Sovrin Blockchain

We are also contributing as the only Africa-based Founding Steward to hosting and testing the Sovrin Blockchain, which is an extremely promising open-source Blockchain development that is specifically designed for digital identity. Participating in the Sovrin network is essential for our roadmap to achieve future interoperability. During Q3 2017 we will set up a live test sandbox node of Sovrin and during Q3 / Q4 2017 develop experimental Sovrin agent applications for ECD use cases. This will inform how we go forward on the future roadmap.


### Roadmap

* **TODO** :star: Service Assurance Bot
* **TODO** :star: Smart contracts Cryptographic currency(AMPS)
* **TODO** :star: Smart contracts Attendance
 

## Built With

* [React Native](https://facebook.github.io/react-native/) - mobile application development
* [PHP laravel](https://laravel.com/) - API 
* [MySQL](https://www.mysql.com/) - database management for mobile application
* [Solidity](https://solidity.readthedocs.io/en/develop/) - smart contracts

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Simon de la Rouviere - Token Smart contract 
