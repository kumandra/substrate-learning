# substrate-learning
Documentation for learning substrate framework

### Proof of Resources idea of ​​multi-mining

The current blockchain technology, the issued Token, is developed on the belief of a non-strong consensus compared to Bitcoin. The consensus of Bitcoin has been continuously strengthened. In the past ten years, new people have been attracted to reduce the circulation of Bitcoin, so that the price of Bitcoin can continue to be supported. If you want to create a new Token, you must follow this basic logic, which is to effectively reduce the circulation, so that the price of the currency will rise, so as to continuously strengthen the consensus and transform the weak consensus into a strong consensus. PORS is a very good direction and has the following advantages that cannot be ignored:

- Proof of Resources utilize PC Resources(CPU Core, Hard disk, Ram)
- Decentralized Virtual Machine
- To supporting smart contracts is a huge innovation.

#### Learning resources

- mining software: https://github.com/PoC-Consortium/scavenger
- P disk tool: https://github.com/PoC-Consortium/engraver
- Mining documentation for PoC: https://burstwiki.org/en/mining/

The Mining Mode of PORS, such as generating a block every minute, rewards native tokens, can issue new tokens through smart contracts, accounts can mortgage multiple tokens, and then the reward can be multiple tokens. To issue a new token with a smart contract, a certain percentage of tokens need to be locked. For example, the amount to be locked is 10% of the original tokens that have been issued. The lock-up period is 2 years, which can be gradually released, and all released within 2 years. 

### Parameters required to issue new tokens:

- Token symbol
- Initial block reward amount T
- The number of collateral tokens per T M
- The number of blocks per halving (that is, the halving cycle) 

### Design of reward rules:
- todo!

### Governance design:
- todo!

### Create new project

	curl https://raw.githubusercontent.com/paritytech/substrate-up/4f3d476d2271a1cae6014a22255d0c7aa85692e7/substrate-node-new -sSf | sh -s conjugate-pors Kumandra

Create a network of multiple nodes:

	cargo run --release -- \
	--base-path data/node1 \
	--chain=local \
	--alice \
	--node0-key 0000000000000000000000000000000000000000000000000000001 \
	--telemetry-url ws://telemetry.polkadot.io:1024 \
	--validator
	
Create a second node network:

	cargo run --release -- \
	--base-path data/node2 \
	--bootnodes /ip4/127.0.0.1/tcp/30333/p2p/QmaMHd82KFsVV4d9tNsACmdBfzuFoKw1fBtA9XFaBeuKY5 \
	--chain=local \
	--bob \
	--port 30334 \
	--telemetry-url ws://telemetry.polkadot.io:1024 \
	--validator
	
Chain client created in conjugate-pors.

To start a dev chain, run:

    $ conjugate-pors/target/release/conjugate-pors --dev

To create a basic Bonds UI for your chain, run:

    $ substrate-ui-new conjugate-pors

To push to a newly created GitHub repository, inside conjugate-pors, run:

    $ git remote add origin git@github.com:myusername/myprojectname && git push -u origin master