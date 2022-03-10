# Stratum V2 Protocol Specification
This repository contains the Stratum V2 protocol specification.

- [0. Abstract](https://github.com/stratum-mining/sv2-spec/blob/main/00-Abstract.md)
- [1. Motivation](https://github.com/stratum-mining/sv2-spec/blob/main/01-Motivation.md)
- [2. Design Goals](https://github.com/stratum-mining/sv2-spec/blob/main/02-Design-Goals.md)
- [3. Protocol Overview](https://github.com/stratum-mining/sv2-spec/blob/main/03-Protocol-Overview.md)
  - [3.1 Data Types Mapping](https://github.com/stratum-mining/sv2-spec/blob/main/03-Protocol-Overview.md#31-data-types-mapping)
  - [3.2 Framing](https://github.com/stratum-mining/sv2-spec/blob/main/03-Protocol-Overview.md#32-framing)
  - [3.3 Protocol Security](https://github.com/stratum-mining/sv2-spec/blob/main/03-Protocol-Overview.md#33-protocol-security)
    - [3.3.1 Motivation for Authenticated Encryption with Associated Data](https://github.com/stratum-mining/sv2-spec/blob/main/03-Protocol-Overview.md#331-motivation-for-authenticated-encryption-with-associated-data)
    - [3.3.2 Motivation for Using the Noise Protocol Framework](https://github.com/stratum-mining/sv2-spec/blob/main/03-Protocol-Overview.md#332-motivation-for-using-the-noise-protocol-framework)
    - [3.3.3 Authenticated Key Agreement Handshake](https://github.com/stratum-mining/sv2-spec/blob/main/03-Protocol-Overview.md#333-authenticated-key-agreement-handshake)
    - [3.3.4 Signature Noise Message](https://github.com/stratum-mining/sv2-spec/blob/main/03-Protocol-Overview.md#334-signature-noise-message)
    - [3.3.5 Certificate Format](https://github.com/stratum-mining/sv2-spec/blob/main/03-Protocol-Overview.md#335-certificate-format)
    - [3.3.6 URL Scheme and Pool Authority Key](https://github.com/stratum-mining/sv2-spec/blob/main/03-Protocol-Overview.md#336-url-scheme-and-pool-authority-key)
  - [3.4 Reconnecting Downstream Nodes](https://github.com/stratum-mining/sv2-spec/blob/main/03-Protocol-Overview.md#34-reconnecting-downstream-nodes)
  - [3.5 Protocol Extensions](https://github.com/stratum-mining/sv2-spec/blob/main/03-Protocol-Overview.md#35-protocol-extensions)
  - [3.6 Error Codes](https://github.com/stratum-mining/sv2-spec/blob/main/03-Protocol-Overview.md#36-error-codes)
  - [3.7 Common Protocol Messages](https://github.com/stratum-mining/sv2-spec/blob/main/03-Protocol-Overview.md#37-common-protocol-messages)
    - [3.7.1 SetupConnection (Client -> Server)](https://github.com/stratum-mining/sv2-spec/blob/main/03-Protocol-Overview.md#371-setupconnection-client---server)
    - [3.7.2 SetupConnection.Success (Server -> Client)](https://github.com/stratum-mining/sv2-spec/blob/main/03-Protocol-Overview.md#372-setupconnectionsuccess-server---client)
    - [3.7.3 ChannelEndpointChanged (Server -> Client)](https://github.com/stratum-mining/sv2-spec/blob/main/03-Protocol-Overview.md#373-channelendpointchanged-server---client)
- [4. Mining Protocol](https://github.com/bitcoin/bips/blob/master/bip-0320.mediawiki)
  - [4.1 Channels](https://github.com/rrybarczyk/sv2-spec/blob/migrate-spec/04-Mining-Protocol.md#411-standard-channels)
    - [4.1.1 Standard Channels](https://github.com/rrybarczyk/sv2-spec/blob/migrate-spec/04-Mining-Protocol.md#411-standard-channels)
    - [4.1.2 Extended Channels](https://github.com/rrybarczyk/sv2-spec/blob/migrate-spec/04-Mining-Protocol.md#412-extended-channels)
    - [4.1.3 Group Channels](https://github.com/rrybarczyk/sv2-spec/blob/migrate-spec/04-Mining-Protocol.md#413-group-channels)
    - [4.1.4 Future Jobs](https://github.com/rrybarczyk/sv2-spec/blob/migrate-spec/04-Mining-Protocol.md#414-future-jobs)
  - [4.2 Hashing Space Distribution](https://github.com/rrybarczyk/sv2-spec/blob/migrate-spec/04-Mining-Protocol.md#42-hashing-space-distribution)

## Authors
Pavel Moravec <pavel@braiins.com>  
Jan Čapek <jan@braiins.com>  
Matt Corallo <bipstratum@bluematt.me>
