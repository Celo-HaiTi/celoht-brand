# Wallet Compatibility Report

## Scope

This repository contains CeloHT brand and documentation assets. It does **not** implement wallet connectivity, blockchain transactions, wallet state management, or product-level wallet logic.

Therefore, this repository does not independently establish or verify runtime wallet compatibility.

Actual wallet compatibility must be verified in the CeloHT application and wallet-integration repositories.

## CeloHT Wallet Strategy

CeloHT follows a **wallet-agnostic strategy**.

The CeloHT dApp is designed to support multiple wallet access methods rather than requiring a single wallet provider.

The current documented wallet integrations include:

- **MiniPay** when the dApp is opened inside MiniPay
- **Valora** through WalletConnect
- **Other compatible mobile wallets** through WalletConnect or another supported wallet integration

Wallet availability and supported functionality may vary by application version, device, wallet provider, network, and integration status.

## Compatibility Matrix

The following matrix describes the **intended/documented integration surface**, not runtime verification performed by this brand repository.

| Capability | Valora | MiniPay | Other WalletConnect-compatible wallets |
| --- | --- | --- | --- |
| Connect | Supported in dApp | Supported when opened inside MiniPay | Supported where WalletConnect integration is available |
| Disconnect | Application-dependent | Application-dependent | Application-dependent |
| Reconnect | Application-dependent | Application-dependent | Application-dependent |
| Celo detection | dApp integration | Injected provider | WalletConnect/provider-dependent |
| Wrong network handling | dApp-dependent | dApp-dependent | dApp-dependent |
| CELO balance | dApp-dependent | dApp-dependent | dApp-dependent |
| USDm balance | dApp-dependent | dApp-dependent | dApp-dependent |
| Transaction signing | Supported through wallet | Supported through wallet | Supported through wallet |
| Confirmation | Wallet-dependent | Wallet-dependent | Wallet-dependent |
| Rejection | Wallet-dependent | Wallet-dependent | Wallet-dependent |
| Error handling | dApp-dependent | dApp-dependent | dApp-dependent |

## Important Distinction

This document must not be interpreted as a claim that every capability above has been independently verified in this repository.

The purpose of this document is to define the **CeloHT wallet compatibility policy and documentation surface**.

Runtime behavior must be verified against the current implementation of the CeloHT dApp and its wallet integration layer.

## Supported Networks

CeloHT's dApp targets:

- **Celo Mainnet**
- **Celo Sepolia**

Wallet compatibility does not imply support for arbitrary networks.

The dApp should reject or clearly handle unsupported networks rather than silently operating on an unintended chain.

## Security

CeloHT does not request or store:

- Seed phrases
- Private keys
- Wallet passwords

Transaction signatures and approvals remain under the user's control inside their selected wallet.

## Non-Affiliation

Listing a wallet or wallet-connectivity technology in CeloHT documentation does not imply a partnership, endorsement, sponsorship, or formal affiliation.

In particular, CeloHT is not officially affiliated with, endorsed by, sponsored by, or operated by Valora, MiniPay, WalletConnect, or their respective developers.

## Verification Sources

For implementation-level verification, consult:

- `celoht-dapp/docs/WALLET_INTEGRATION.md`
- `celoht-dapp/SUPPORTED_WALLETS.md`
- `celoht-dapp` wallet integration source code
- Current application deployment and end-to-end wallet tests

## Conclusion

This repository does not implement wallet functionality and therefore cannot independently certify runtime wallet compatibility.

CeloHT's documented strategy is **wallet-agnostic**, with support for MiniPay, Valora, and other compatible wallet integrations subject to the actual dApp implementation and current integration availability.

## Final Status

**Repository scope:** Documentation and brand policy only.

**Wallet runtime compatibility:** Not implemented or verified in this repository.

**CeloHT wallet strategy:** Wallet-agnostic.