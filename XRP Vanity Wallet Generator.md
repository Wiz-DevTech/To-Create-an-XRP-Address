XRP Vanity Wallet Generator

A Node.js CLI tool for generating XRP Ledger vanity addresses by brute-forcing wallet keys until a matching pattern is found.

⚠️ Disclaimer

This tool generates cryptographic keypairs locally.
Anyone who has access to a generated secret (seed) fully controls the wallet on the XRP Ledger.

Never share generated secrets.

📦 Requirements
Node.js (recommended: LTS 18 or 20)
npm

Check versions:

node -v
npm -v
📥 Installation

Clone or download the project:

git clone <https://github.com/Wiz-DevTech/To-Create-an-XRP-Address.git>
cd xrp-vanity-generator

Install dependencies:

npm install
🚨 Windows PowerShell Fix (if needed)

If you see this error:

npm.ps1 cannot be loaded because running scripts is disabled

Run:

Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass

Then retry:

npm install
🚀 Usage

Run the generator:

node index.js <workers> <keyword1> <keyword2> ...
Example
node index.js 4 xr xrp
What this means:
4 = number of worker processes (CPU threads)
xr xrp = keywords to search for in addresses
🔍 Output Example
> Match: [ X72xE8VmvsMxrwXTg7tcdEJhb5KGimVND9AmqJGMtqkisXr ] 
  (rsG86FCygfUZSCEJfnRUzNDdKsNWAgvczJ)
  with secret [ sncA5kpUFME4sNHDcTHchpHBzqND3 ]
🔑 What the results mean
X-address / Classic address → public wallet identifier
Secret (seed) → private key (full wallet control)

If someone has the secret, they control the wallet.

💳 How to use a generated wallet
Copy the X-address into a wallet or exchange
Fund it (≈10 XRP minimum reserve on XRPL)
Wallet becomes active on-chain
Use your secret to access/control it in compatible wallets
⚙️ Notes
Longer keywords = exponentially slower generation
Matches are found via brute-force key generation
CPU usage will be high (multi-worker design)
🛑 Stop the program

Press:

Ctrl + C
🧠 Tip

For best performance:

Use Node.js LTS (not bleeding-edge versions)
Match shorter patterns first (xr, xrp, etc.)
