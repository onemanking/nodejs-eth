# nodejs-eth

1. npm i
2. touch .env to create .env file to setup env
    ```js
    API_KEY = 'INFURA API KEY'
    NETWORK = 'ropsten'
    PORT = 3000
    PRIVATE_KEY = 'PRIVATE KEY'
    KEYSTORE = JSON OBJECT KEYSTORE V3 
    PASSWORD = 'KEYSTORE PASSWORD'
    ````
3. npm start
4. use postman
    - GET : /v1/wallet/getBalance/?walletAddress=YOURADDRESS : to get wallet balance
    - GET : /v1/ether/getGasPrice : to get current gas price
    - POST : /v1/wallet/sendEth require body with keystoreV3, password, addressList and amount : to send ether with Keystore
    ```js
    { 
        "keystore": {
            "version": 3,
            "id": "04e9bcbb-96fa-497b-94d1-14df4cd20af6",
            "address": "2c7536e3605d9c16a7a3d7b1898e529396a65c23",
            "crypto": {
                "ciphertext": "a1c25da3ecde4e6a24f3697251dd15d6208520efc84ad97397e906e6df24d251",
                "cipherparams": {
                    "iv": "2885df2b63f7ef247d753c82fa20038a"
                },
                "cipher": "aes-128-ctr",
                "kdf": "scrypt",
                "kdfparams": {
                    "dklen": 32,
                    "salt": "4531b3c174cc3ff32a6a7a85d6761b410db674807b2d216d022318ceee50be10",
                    "n": 262144,
                    "r": 8,
                    "p": 1
                },
                "mac": "b8b010fff37f9ae5559a352a185e86f9b9c1d7f7a9f1bd4e82a5dd35468fc7f6"
            }
        },
        "password": "testPassword", 
        "addressList": ["0xF092765161d6a81599983987105E72fD084c2fe5", "0xc9181293bA18A023dEd8Bf53B54C0A9c70597063"],
        "amount": 0.005
    }
    ```
    - POST : /v1/wallet/sendEthWithPk require body with addressList and amount : to send ether with Private Key
    ```js
    { 
        "addressList": ["0xF092765161d6a81599983987105E72fD084c2fe5", "0xc9181293bA18A023dEd8Bf53B54C0A9c70597063"],
        "amount": 0.005
    }
    ```
