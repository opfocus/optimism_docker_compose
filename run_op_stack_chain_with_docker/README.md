# Run a op stack chain with docker
Please note that this file should be used in conjunction with the op-stack documentation. **It is not intended for a one-click startup of the op-stack chain**. I have limited knowledge of Docker, so it may not be fully mature. However, I have conducted as many tests as possible. 

Here is an overview:
- It includes the process of initializing op-geth using genesis.json.
- After the initial initialization, a marker file is generated to prevent repeated initialization.
- op-node is delayed by 20 seconds to avoid early startup, which could result in communication being denied with op-geth.

Important Notes:
1. In the absence of genesis.json, the op-geth log will display the following message:
`root-op-geth-1  | Please generate your genesis.json file following the documentation steps.`
2. At this point, two folders, 'datadir' and 'genesis.json'  have been generated in the op-geth directory and need to be manually deleted to - prepare for the correct content generation.
`rm -rf  datadir  genesis.json`
3. Use `docker-compose down --volumes` to remove the containers, and then restart.

Resource
- [op-stack doc](https://stack.optimism.io/docs/build/getting-started/) <br>
- [stopping your Rollup](https://stack.optimism.io/docs/build/operations/#stopping-your-rollup) <br>
- [op-node\op-bather\op-proposer images](https://github.com/ethereum-optimism/optimism/releases) <br>
- [op-geth image](https://github.com/ethereum-optimism/op-geth/releases)
