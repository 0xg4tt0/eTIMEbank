# eTIMEbank

` work in progress `

This is a **Proof of Concept** fork of the [Cashu Development Kit (cdk)](https://github.com/cashubtc/cdk) in an attempt to apply a [Chaumian blinded signatures scheme](https://wikipedia.org/wiki/Blind_signature) to the concept of [Time Banking](https://en.wikipedia.org/wiki/Time_banking). 

This project was be submitted to a [Bitcoin++ Hackathon](https://btcplusplus.dev/) you are free to fork it & PRs welcome.

By design this project does not include any Bitcoin, Lightning, or Nostr elements within its code and does not use satoshis as a unit within the mint.

### To know more about the [design choices, time banking, and the reasoning hbehind this project refer to the context.md document within this repository](https://github.com/0xg4tt0/eTIMEbank/blob/main/context.md)


## TO DO

- [x] fork cdk & write project description
- [x] write context.md
- [x] remove Lightning Network logic:
  - [x] cdk-lnbits
  - [x] cdk-lnd
  - [x] cdk-phoenixd
  - [x] cdk-strike
  - [x] cdk-cln
  - [x] cdk-integration-tests
  - [x] cdk-rexie
  - [x] cdk-sqlite
- [x] remove Bitcoin logic:
- [x] LN invoice logic
- [x] nostr logic
- [x] removed alternative database options (chose redb as local.storage / database)
- [ ] customise 'fake-wallet' into 'etime-wallet'
- [ ] replace 'sats' with 'time'
  - [ ] define 'time' (unix_time)
  - [ ] create code for timer output to mint quote
  - [ ] generates 'etime' from mint quote (melt)
  - [ ] reciever claims 'etime'
  - [ ] test code additions
- [ ] cdk-mintd customisation
  - [ ] Mint has limited supply with only faucet wallet can call mint function
  - [ ] disable minting unless you are the faucet wallet
  - [ ] the mint can only do swaps of aready minted enotes
  - [ ] copy etime-wallet and make faucet-wallet with mint logic
- [ ] testing
- [ ] deploy on 2 devices
- [ ] test sharing 'time' between 2 devices
- [ ] release


## Design choices for project

- 100% offline use (no http/API)
- should run on smartphones made after 2010 (ideally a PWA)
- access-control to the mint (not open to anyone)
- etime notes represent minutes of real time (time counter mechanism)
- no 'withdrawl' or 'deposit' logic (no exchange of etime for other assets)
- ability to cryptographically query the mint for unique audits (more transparency with verifiability)

## Specifications

*meow*
*meow*


## Relevnt NUTs

*meow*
*meow*


## Feature Request / Future

- QR for mint invite with associated metadata for who invited them to mint / access-control
- Extra step: giver of etime submits quote to mint, presents etime to reciever, receiver claims etime. (more code needed)
- Setup wizard process for mint operators to select the appropriate setup for their community
- multi-mint or federated setup of mints within wallet client (Fedi example)
- LoRA / mesh network / bluetooth connectivity protocol for clients (offline)
- APK build
- reproducible build testing
- Translate into multiple languages (not just European ones)

## How to deploy / build

*meow*
*meow*


## License

Code is under the [MIT License](LICENSE)

## Hackathon timeline 
Timezone: GMT+2
- 12 Oct 2024 - 10:57 - [Init commit ](https://github.com/0xg4tt0/eTIMEbank/commit/4dbffba344d1a2e2e41d63d61234069f4bbf64c9)
- 12 Oct 2024 - 16:26 - [finished project description / context](https://github.com/0xg4tt0/eTIMEbank/commit/99625bdf569348f27058bf4c27e364b67022193c)
- 12 Oct 2024 - 17:09 - [started 'trimming the fat' from crates and logic](https://github.com/0xg4tt0/eTIMEbank/commit/e960058780e15fa89661ab3c17c470da3fda8434)
- 12 Oct 2024 - 17:54 - the rust code compiled without errors!
- 12 Oct 2024 - 18:03 - [merged thesimplekid fixes](https://github.com/0xg4tt0/eTIMEbank/pull/1)
- 12 Oct 2024 - 18:04 - drink beer
- 12 Oct 2024 - 20:20 - [refined context.md and roadmapped next steps on readme.md](https://github.com/0xg4tt0/eTIMEbank/commit/b8eea10f25359118aacffdc7e316bf2dc85902cd)

# Archive of the original README.md from cdk fork

```

> **Warning**
> This project is in early development, it does however work with real sats! Always use amounts you don't mind loosing.


# Cashu Development Kit

CDK is a collection of rust crates for [Cashu](https://github.com/cashubtc) wallets and mints written in Rust.

**ALPHA** This library is in early development, the api will change and should be used with caution.


## Project structure

The project is split up into several crates in the `crates/` directory:

* Libraries:
    * [**cdk**](./crates/cdk/): Rust implementation of Cashu protocol.
    * [**cdk-sqlite**](./crates/cdk-sqlite/): SQLite Storage backend.
    * [**cdk-redb**](./crates/cdk-redb/): Redb Storage backend.
    * [**cdk-rexie**](./crates/cdk-rexie/): Rexie Storage backend for browsers.
    * [**cdk-axum**](./crates/cdk-axum/): Axum webserver for mint.
    * [**cdk-cln**](./crates/cdk-cln/): CLN Lightning backend for mint.
    * [**cdk-lnd**](./crates/cdk-lnd/): Lnd Lightning backend for mint.
    * [**cdk-strike**](./crates/cdk-strike/): Strike Lightning backend for mint.
    * [**cdk-lnbits**](./crates/cdk-lnbits/): [LNbits](https://lnbits.com/) Lightning backend for mint.
    * [**cdk-fake-wallet**](./crates/cdk-fake-wallet/): Fake Lightning backend for mint. To be used only for testing, quotes are automatically filled.
* Binaries:
    * [**cdk-cli**](./crates/cdk-cli/): Cashu wallet CLI.
    * [**cdk-mintd**](./crates/cdk-mintd/): Cashu Mint Binary.


## Implemented [NUTs](https://github.com/cashubtc/nuts/):

### Mandatory

| NUT #    | Description                       |
|----------|-----------------------------------|
| [00][00] | Cryptography and Models           |
| [01][01] | Mint public keys                  |
| [02][02] | Keysets and fees                  |
| [03][03] | Swapping tokens                   |
| [04][04] | Minting tokens                    |
| [05][05] | Melting tokens                    |
| [06][06] | Mint info                         |

### Optional

| # | Description | Status
| --- | --- | --- |
| [07][07] | Token state check | :heavy_check_mark: |
| [08][08] | Overpaid Lightning fees | :heavy_check_mark: |
| [09][09] | Signature restore | :heavy_check_mark: |
| [10][10] | Spending conditions | :heavy_check_mark: |
| [11][11] | Pay-To-Pubkey (P2PK) | :heavy_check_mark: |
| [12][12] | DLEQ proofs | :heavy_check_mark: |
| [13][13] | Deterministic secrets | :heavy_check_mark: |
| [14][14] | Hashed Timelock Contracts (HTLCs) | :heavy_check_mark: |
| [15][15] | Partial multi-path payments (MPP) | :heavy_check_mark: |
| [16][16] | Animated QR codes | :x: |
| [17][17] | WebSocket subscriptions  | :construction: |

MSRV

## Bindings

Experimental bindings can be found in the [bindings](./bindings/) folder.

## License

Code is under the [MIT License](LICENSE)

## Contribution

All contributions welcome.

Unless you explicitly state otherwise, any contribution intentionally submitted for inclusion in the work by you, shall be licensed as above, without any additional terms or conditions.

[00]: https://github.com/cashubtc/nuts/blob/main/00.md
[01]: https://github.com/cashubtc/nuts/blob/main/01.md
[02]: https://github.com/cashubtc/nuts/blob/main/02.md
[03]: https://github.com/cashubtc/nuts/blob/main/03.md
[04]: https://github.com/cashubtc/nuts/blob/main/04.md
[05]: https://github.com/cashubtc/nuts/blob/main/05.md
[06]: https://github.com/cashubtc/nuts/blob/main/06.md
[07]: https://github.com/cashubtc/nuts/blob/main/07.md
[08]: https://github.com/cashubtc/nuts/blob/main/08.md
[09]: https://github.com/cashubtc/nuts/blob/main/09.md
[10]: https://github.com/cashubtc/nuts/blob/main/10.md

```
[11]: https://github.com/cashubtc/nuts/blob/main/11.md
[12]: https://github.com/cashubtc/nuts/blob/main/12.md
[13]: https://github.com/cashubtc/nuts/blob/main/13.md
[14]: https://github.com/cashubtc/nuts/blob/main/14.md
[15]: https://github.com/cashubtc/nuts/blob/main/15.md
[16]: https://github.com/cashubtc/nuts/blob/main/16.md
[17]: https://github.com/cashubtc/nuts/blob/main/17.md
