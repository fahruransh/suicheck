# suicheck

Check Sui wallet balances in bulk via a Sui JSON-RPC endpoint.

## How it works

Put Sui wallet addresses in `wallet.txt` (one per line), run the script, and every address
that holds a balance is saved to `wallet_ada_balance.txt`. Checks run with 5 parallel workers,
a 3-second delay between checks, and up to 2 retries per address.

## Requirements

- Python 3
- A Sui JSON-RPC endpoint URL

## Setup

```bash
pip install requests
```

Open `suicheck.py` and set `RPC_URL` to your own Sui RPC endpoint (it ships as a placeholder).

## Usage

```bash
python suicheck.py
```

1. Add Sui addresses to `wallet.txt`, one per line.
2. Run `python suicheck.py`.
3. Check `wallet_ada_balance.txt` for addresses with a balance (shown in SUI in the terminal output).

## Tech

- Python
- `requests`
- Sui JSON-RPC (`suix_getBalance`)
