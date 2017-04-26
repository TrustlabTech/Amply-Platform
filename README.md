# Amply-Trustlab

<img src="https://cloud.githubusercontent.com/assets/25197053/24645519/bbfcedd0-1918-11e7-9763-a42d9d4935c5.jpg" alt="Amply Logo" width="150" height="150">

Amply is for Early Childhood Development service-delivery. Amply for ECD provides verified digital registries of ECD Service Providers, ECD centres and the children who are eligible beneficiaries. Service delivery records are captured as verifiable claims. Each service transaction generates a digital cryptographic token that can be exchanged for value, such as a government subsidy or social impact bond payment. The personal data collected through this service delivery are managed using the Consent Protocol, which enables consented sharing of personal information between trusted identities

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

This enables form-based data to be captured and submitted using the Amply Mobile Application (for instance, an attendance form), to replace paper-based data capture. This data is compiled into a Verifiable Claim format that is cryptographically signed by the service provider (ECD practitioner) submitting the claim through the Mobile App. This creates accountability for the data capture and generates a record that cannot be repudiated or changed. A 3rd Party Identity Verification Integration. Allows for Department of Home Affairs verification of Identity Number, Name, Surname, DOB, Gender and Alive Status thus this creates a verified registry of ECD staff and children.

Attendance Claim which is a verifiable claim, this data includes the identifier of the service-provider, the nature of the service, date and time, identifiers of the beneficiaries (children) and other relevant information. These data generate a Claim Hash, which is a unique fingerprint of the data. The Claim Hash could be considered a digital asset, as this represents the authenticity and proof of a claim.Security data such as the GPS location are also captured by the mobile application, to validate the claim. On submission of a claim, the Mobile Application triggers a transaction in the Blockchain using the AMP Token-generator DApp, into which it inserts the Claim Hash.The claim data are encrypted and transmitted to the ECD Enterprise Staging Server. (In future, claim data will be submitted directly to each ECD Centre’s Data Store, from where it will only be accessible with the consent of the ECD Centre controller).

Cryptographic Tokens can be designed to represent value on a Blockchain. In the Amply system, we call these tokens AMPs. One AMP represents one service unit claim (for instance the claim by a service provider that ‘I delivered an early learning service to one child’). Each token is recorded together with a cryptographic hash of its metadata - including the service provider’s ID, time, location, beneficiary IDs and type of service delivered. This means that data associated with a claim cannot be repudiated or defrauded. We have designed the data specification for an Ethereum Smart Contract token generator DApp that automatically issues AMPs to an ECD centre’s Blockchain address when a transaction is initiated by the Amply Mobile App. This transaction is triggered by a registered ECD service provider (ECD practitioner) digitally signing an attendance claim using the App.

## Service Provider Wallet Manager Module	

Each ECD centre will be registered with a Decentralised Identity on the Ethereum Blockchain. This creates a ‘wallet’ address to which tokens can be sent. Securing this Service Provider Wallet requires management of the cryptographic keys that are used to sign Blockchain transactions. The Wallet Manager module will provide key management capabilities through a web interface.

## Attendance Smart Oracle Module

The Amply Attendance Smart Oracle is a software agent that processes the information it receives and check that this meets the criteria for verifying a claim. This checks that all the identifiers in a claim are valid and have not been duplicated. It references the Blockchain transaction that was created and checks that the data received matches the Claim Hash in the transaction record. Security information that was sent by the mobile app and checks this against expected parameters such as matching the GPS location where the attendance record was taken with the GPS location of the ECD centre.Once all the required checks have been passed, the Smart Oracle digitally signs the claim to verify that it is valid and this automatically allows related exchange transactions on the Blockchain to proceed. If a claim is rejected by the Oracle, it produces reason codes that can be viewed through an administration module.

## Decentralised AMPs Exchange Module

The Decentralised Exchange is an Ethereum DApp that enables anyone to offer a cryptographic token in exchange for AMPs. For an exchange transaction to complete requires that the transaction must be signed by the Attendance Smart Oracle.The Claim Hash within the transaction that was created at the time of a service provider submitting their claim with the Claim Hash that has been signed by the Attendance Smart Oracle.

## Reporting Dashboard Module

Service delivery transactions recorded on the blockchain will be viewed using a web application blockchain explorer. This will provide real-time information, such as an indication of the number of children receiving ECD services, based on claims submitted through the Amply Mobile Application.

## ECD Enterprise Staging Server
The ECD Enterprise Staging Server will be connected to the Consent API (Application Programming Interface) through the Consent Connector application. This will enable data that is collected through the Amply Mobile Application (such as identity registration fields) to be transmitted into Personal Data Stores, where this becomes the property of the identity subject.

## Mobile Application

The Amply Mobile application will compile Verifiable Claims with cryptographic signatures and perform other hashing and encryption processes. This will include an Ethereum light wallet (using available open-source code) to enable the App to communicate directly with the Ethereum Blockchain for initiating transactions in the AMP Token-Generator DApp.

## Sovrin Blockchain

We are also contributing as the only Africa-based Founding Steward to hosting and testing the Sovrin Blockchain, which is an extremely promising open-source Blockchain development that is specifically designed for digital identity. It is our opinion that DID registrations should be Blockchain-agnostic, as each Blockchain serves a specific purpose. Participating in the Sovrin network is essential for our roadmap to achieve future interoperability. 


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
