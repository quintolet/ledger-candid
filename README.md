# Missing Candid Interface to the NNS Ledger Canister

The [NNS ledger canister] on the Internet Computer offers both Candid and Protobuf interfaces.
However the candid interface is missing some important utlities, e.g. reading data of a past transactions.

To solve the problem, we provide the following missing interfaces in Candid by proxying the call to the NNS ledger and translating between the data formats:

```
service : {
  block : (nat64) -> (variant { Ok: variant { Ok: Block; Err: CanisterId }; Err: text });
  tip_of_chain : () -> (variant { Ok: TipOfChain; Err: text });
}
```

The complete interface can be looked up on [ic.rocks] or [canlista].
