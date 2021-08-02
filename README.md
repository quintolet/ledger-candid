# Missing Candid Interface to the NNS Ledger Canister

The [NNS ledger canister] on the Internet Computer offers both [Candid] and [Protobuf] interfaces.
However the candid interface is missing some important utilities, including looking up a past transaction.

To solve this problem, we provide the following missing interfaces in Candid by proxying the call to the NNS ledger and translating between the data formats:

```
service : {
  block : (nat64) -> (variant { Ok: variant { Ok: Block; Err: CanisterId }; Err: text });
  tip_of_chain : () -> (variant { Ok: TipOfChain; Err: text });
}
```

The complete interface can be found in source file [ledger_candid.did] or canister [ockk2-xaaaa-aaaai-aaaua-cai] on ic.rocks.

[NNS ledger canister]: https://ic.rocks/principal/ryjl3-tyaaa-aaaaa-aaaba-cai
[Candid]: https://ic.rocks/interfaces/nns/ledger.did
[Protobuf]: https://ic.rocks/interfaces/nns/ledger.proto
[ockk2-xaaaa-aaaai-aaaua-cai]: https://ic.rocks/principal/ockk2-xaaaa-aaaai-aaaua-cai
[ledger_candid.did]: https://github.com/quintolet/ledger-candid/blob/main/ledger_candid.did
[canlista]: https://k7gat-daaaa-aaaae-qaahq-cai.ic0.app/listing/ledger-candid-10278
