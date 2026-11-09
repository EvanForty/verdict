# VERDICT

The prediction market of everything, built on Elysium.

VERDICT is a decentralized prediction market where anyone can create and trade YES/NO markets on crypto, politics, technology, sports, internet culture and the Elysium ecosystem.

Ticker: **$VERDICT** · X: [@TradeOnVerdict](https://x.com/TradeOnVerdict)

## Files

| File | What it is |
|------|------------|
| `index.html` | The whole site: HTML, CSS and JavaScript in one file |
| `logo.png` | VERDICT logo, used as the favicon and social preview |
| `README.md` | This file |

## Run locally

Wallet extensions only inject on `http://` or `https://` pages, not `file://`. Serve the folder:

```bash
npx serve .
# or
python3 -m http.server 8000
```

Then open http://localhost:8000 (or the port shown).

## Deploy with GitHub Pages

1. Push these files to the root of your repo's `main` branch.
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, pick `main` and `/ (root)`, and save.
4. Your site will be live at `https://<username>.github.io/<repo>/` within a minute or two.

To use a custom domain, add it under **Settings → Pages → Custom domain**.

## Wallets

Connect wallet supports MetaMask, Phantom, Rabby, Coinbase Wallet, OKX, Rainbow and any other EVM wallet that follows EIP-6963, with a fallback for older injected wallets. On mobile, wallets that aren't installed get an "Open in app" deep link.

## Configuration

Search `index.html` for these and update before launch:

- `ELYSIUM={chainId:null,symbol:'HYPE'}`: set `chainId` to Elysium's chain ID in hex (for example `'0x1234'`) so balances on Elysium are labelled HYPE.
- `doTrade()`: orders are currently signed with `personal_sign` and recorded in the browser. Replace the signing step with your market contract calls to settle trades on-chain.
- `markets = [...]`: the market list and odds. Replace with data from your contracts or indexer.

## Next steps

- Connect market creation, trading and settlement to the VERDICT smart contracts.
- Load live market data from an indexer instead of the built-in list.
- Add WalletConnect (requires a project ID from WalletConnect Cloud) for QR-code connections from mobile wallets.
