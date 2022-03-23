# simple-blockchain-transactions
A decentralized blockchain and coin transactions

mine_block GET request connect to PORT 5001:
```{
    "index": 2,
    "message": "Congratulations, you just mineed a block",
    "previous_hash": "b949089443efb17e91622662eb7ff579a54ae00058b0a4ef43ddabb3c28a7c24",
    "proof": 533,
    "timestamp": "2022-03-23 14:19:18.656140",
    "transactions": [
        {
            "amount": 10,
            "receiver": "Mateus",
            "sender": "617016fce66e468faf32c6e2ca8a2e02"
        }
    ]
}
```

replace_chain GET request connect to PORT 5002:
```
{
    "message": "Node had different chain, chain is now replaced",
    "new_chain": [
        {
            "index": 1,
            "previous_hash": "0",
            "proof": 1,
            "timestamp": "2022-03-23 14:17:47.897703",
            "transactions": []
        },
        {
            "index": 2,
            "previous_hash": "b949089443efb17e91622662eb7ff579a54ae00058b0a4ef43ddabb3c28a7c24",
            "proof": 533,
            "timestamp": "2022-03-23 14:19:18.656140",
            "transactions": [
                {
                    "amount": 10,
                    "receiver": "Mateus",
                    "sender": "617016fce66e468faf32c6e2ca8a2e02"
                }
            ]
        }
    ]
}
```
mine_block on PORT 5002 and GET request replace_chain on PORT 5003:
```
{
    "chain": [
        {
            "index": 1,
            "previous_hash": "0",
            "proof": 1,
            "timestamp": "2022-03-23 14:17:47.897703",
            "transactions": []
        },
        {
            "index": 2,
            "previous_hash": "b949089443efb17e91622662eb7ff579a54ae00058b0a4ef43ddabb3c28a7c24",
            "proof": 533,
            "timestamp": "2022-03-23 14:19:18.656140",
            "transactions": [
                {
                    "amount": 10,
                    "receiver": "Mateus",
                    "sender": "617016fce66e468faf32c6e2ca8a2e02"
                }
            ]
        },
        {
            "index": 3,
            "previous_hash": "5fb42c6683edeff43fa7333ba535f86b961e5b889ef54bbeef717aed83410626",
            "proof": 45293,
            "timestamp": "2022-03-23 14:22:48.375366",
            "transactions": [
                {
                    "amount": 10,
                    "receiver": "User01",
                    "sender": "0b23e332f4244afa9db1628255a5910e"
                }
            ]
        }
    ],
    "lenght": 3
}
```
