# solana-nfts-mint-with-sugar-metaplex

### Setup Sugar

bash <(curl -sSf https://sugar.metaplex.com/install.sh)
sugar --version

### Setup wallets

# Setup Solana Tool Suite
sh -c "$(curl -sSfL https://release.solana.com/v1.10.32/install)"
solana --version

# HabYged3f8PHvkgU5i8KksdowMTxJ8a8t2Mbeapf4347
solana-keygen new --outfile ./wallets/Owner.json

# 7aL8PDzc9dbohjoXnFZdC7nnYZwS7bK9QNnRuHYXbXgc
solana-keygen new --outfile ./wallets/Treasury.json

# DXXYo4hbw3Ae13Y2P67eLmmq1tPFpR39BjieiLCJNium
solana-keygen new --outfile ./wallets/Creator.json

solana config set --keypair ~/KeyStrokes/nft/wallets/Owner.json
solana config set --url https://metaplex.devnet.rpcpool.com/

### Prepare Assets

curl https://docs.metaplex.com/assets/files/assets-ff6bd873ecd07b49c86faf3c7aab82d2.zip --output ./assets.zip

unzip assets.zip

### Launch Interactive Setup

# Candy Machine ID: 3QNr5BfoTZ42YGWVsyDbBPosjjDgYGPmR47T5rWYG6oW
sugar launch

### Setup Candy Machine UI

git clone https://github.com/metaplex-foundation/candy-machine-ui ./candy-machine-ui/

cd ./candy-machine-ui/

yarn install

cp .env.example .env

yarn start
