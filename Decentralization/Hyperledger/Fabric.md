# 1. What is Hyperledger?
  - “Hyperledger is an open source collaborative effort created to advance cross-industry Blockchain technologies. It is a global collaboration, hosted by The Linux Foundation, including leaders in finance, banking, Internet of Things, supply chains, manufacturing, and Technology.”
  - In December 2015, the Linux Foundation announced the creation of the Hyperledger Project. 
  - Brian Behlendorf  was appointed executive director of the project. 
  - Note: Hyperledger does not support Bitcoin or any other cryptocurrency. But the platform is thrilled by Blockchain technology.
# 2. Hyperledger Frameworks
  - Hyperledger FABRIC
  - Hyperledger BURROW
  - Hyperledger CELLO
  - Hyperledger EXPLORER
  - Hyperledger IROHA
  - Hyperledger CALIPER
  - Hyperledger COMPOSER
  - Hyperledger INDY
  - Hyperledger QUILT
  - Hyperledger SAWTOOTH
# 3. What is Hyperledger Fabric?
  - Hyperledger fabric is intended as a foundation for developing applications or solutions with a modular architecture, Hyperledger fabric allows components such as consensus and membership services, to be plug-and-play. Hyperledger Fabric leverages container technology to host smart contracts called “chaincode” that comprise the application logic of the system.
  - Hyperledger Fabric was initially contributed by Digital Asset and IBM, as a result of the first hackathon.
# 4. Things to know..!
  - Channel
  - Certificate Authority ( CA )
  - Peer
  - Orderer
  - Endorser
# 5. Channel
  - A data partitioning mechanism to control transaction visibility only to stakeholders 
  - Consensus takes place within a channel by members of the channel 
  - Other members on the network are not allowed to access the channel and will not see transactions on the channel 
  - A chaincode may be deployed on multiple channels, each instance is isolated within its channel
  - A chaincode may query another chaincode in other channel (ACL applied)
# 6. Certificate Authority ( CA )
- A certificate authority (CA) is a trusted entity that issues electronic documents that verify a digital entity's identity on the Internet. The electronic documents, which are called digital certificates, are an essential part of secure communication and play an important part in the public key infrastructure
  - Default implementation of the Membership Services Provider Interface.
  - Issues Ecerts (long-term identity) and Tcerts (disposable certificate)
  - Supports clustering for HA characteristics
  - Supports LDAP for user authentication
  - Supports HSM
# 7. Peer
  - A Peer is a node on the network maintaining state of the ledger and managing chaincodes 
• Any number of Peers may participate in a network
 • A Peer can be an endorser, committer and/or submitter (submitter has not been implemented). An endorser is always a committer
	 – An endorser executes and endorses transactions
	 – A committer verifies endorsements and validates transaction results 
• A Peer manages event hub and deliver events to the subscribers 
• Peers form a peer-to-peer gossip network

