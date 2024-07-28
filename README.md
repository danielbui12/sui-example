## Sui example

- Get active address

```sh
sui client active-address
```

- Switch to address

```sh
sui client switch --address 0xfb6ce11d8c97c64d3d07804bf32234f29efec967b701e061f510f06c502d8754
```

- Request gas 

```sh
curl --location --request POST 'https://faucet.devnet.sui.io/gas' \
--header 'Content-Type: application/json' \
--data-raw '{
    "FixedAmountRequest": {
        "recipient": "0xfb6ce11d8c97c64d3d07804bf32234f29efec967b701e061f510f06c502d8754"
    }
}'
```

- Build

```sh
sui move build
```

- Test

```sh
sui move test
```

- Deploy

```sh
sui client publish
```

- Call a function

```sh
sui client ptb \
	--assign forge @0xe4c28c23b80d046679b427a16e079d6c3840ecebc74e0f0083b640789a22e578 \
	--assign to_address @0xfb6ce11d8c97c64d3d07804bf32234f29efec967b701e061f510f06c502d8754 \
	--move-call 0xe4c28c23b80d046679b427a16e079d6c3840ecebc74e0f0083b640789a22e578::example::new_sword forge 10 3 \
	--assign sword \
	--transfer-objects "[sword]" to_address \
	--gas-budget 20000000
```

