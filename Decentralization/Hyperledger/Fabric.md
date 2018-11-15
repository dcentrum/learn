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
- Any number of Peers may participate in a network
- A Peer can be an endorser, committer and/or submitter (submitter has not been implemented). An endorser is always a committer
   – An endorser executes and endorses transactions
   – A committer verifies endorsements and validates transaction results 
- A Peer manages event hub and deliver events to the subscribers 
- Peers form a peer-to-peer gossip network
# 8. Orderer
- A group of Orderers runs a communication service, called ordering service, to provide atomic broadcast
- Provides ordering of operations, before the data is committed in the ledger it has to pass through the orderer.
- Orderer will creates the blocks, that will be part of the Blockchain.
- Once the block is full, orderer will send the blocks to the peers, peers will commit to the block to the ledger.
- Ordering service is responsible for:
  - Verification.
  - Security.
  - Policy management.
# 9. Transaction Endorsement
- An endorsement is a signed response of the result of a transaction execution 
- An endorsement policy encapsulates the requirement for a transaction to be accepted by the stakeholders, either explicit or implicit 	    – A signature from both member1 and member2
	 – Either a signature from both member1 and member2 or a signature from member3 
	 – A signature from John Doe
- The endorsement policy is specified during a chaincode instantiation on a channel; each channel-chaincode may have different endorsement policy
# 10. Chaincode
- A chaincode is programmatic code deployed on the network, where it is executed and validated by chain validators together during the consensus process.  
- Developers can use chaincode's to develop business contracts, asset definitions, and collectively-managed decentralized applications
- There are generally two ways to develop business contracts: the first way is to code individual contracts into standalone instances of chaincode; the second way, and probably the more efficient way, is to use chaincode to create decentralized applications that manage the life cycle of one or multiple types of business contracts, and let end users instantiate instances of contracts within these applications. 
- Chaincode can be written in any programming language and executed in containers. The first fully supported chaincode language is Golang. 
# 11. Membership Service Providers(MSP)
- An abstraction of identity provider
	 – <MSP.id, MSP.sign, MSP.verify, MSP.validateid, MSP.admin>
	 – govern application, endorser and orderer identities
- Used as building blocks for access control frameworks 
	– at the system level (read/write access on system controls, 	    and channel creation) – at the channel level (read/write     	     access), 
	– at the chaincode level (invocation access) 
- Represent a consortium or a member
# 12. Hyperledger Architecture
- IDENTITY
  - Pluggable, Membership, Privacy and Auditability of transactions.

- LEDGER | TRANSACTIONS
  - Distributed transactional ledger whose state is updated by consensus of stakeholders

- SMART-CONTRACT
  - “Programmable Ledger”, provide ability to run business logic against the blockchain (aka smart contract)

- APIs, Events, SDKs
  - Multi-language native SDKs allow developers to write DLT apps 
# 13. Ledger
- In Hyperledger fabric State database options include LevelDB and Couch DB.
- LevelDB is the default state database embedded in the peer process and stores chaincode data as key-value pairs. 
- CouchDB can store any binary data that is modeled in chaincode .But as a JSON document store, CouchDB additionally enables rich query against the chaincode data, when chaincode values (e.g. assets) are modeled as JSON data.
# 14. Bootstrapping a Network
- Decide on members (MSPs) controlling the ordering service
 – Set up MSP configuration for each member (root certs, signing certs, key, admins)
 – Set up policies governing the network (who has privilege to modify config and create channels)
 – Start up orderers with the configuration
- Each member decides on the number of peers to participate – For each peer, issue peer identity (local MSP configuration) and start it up
- At this point, we have a network of peers and orderers – Peers are not yet connected to orderers nor to each other
