# mint txn merge
This tool takes two Mint.com transactions.csv from two different periods, merges and removes duplicates.
This tool may be unfinished and have bugs, please double-check its work and offer bug reports / pull requests.

TODO:
- Everything
- For merge-mode: If txn doesn't exist in newest, count it as removed, and remove it from result. Unless `[-n | --nodelete]` is passed.
- For diff-mode: If txn doesn't exist in newest, warn about it being removed (we can't have a "negative" entry). Unless `[-n | --nodelete]` is passed.
- Create/standardize this help output to something way more unix-like.

Usage (merge): `mint_txn_merge.py <oldest_transactions.csv> <newest_transactions.csv> <output.csv>`
Usage (diff): `mint_txn_merge.py -d <oldest_transactions.csv> <newest_transactions.csv> <output.csv>`
Options:
- `[-d | --diff]` act in diff mode, only producing a list of new ledger entries rather than a merge.
- `[-b | --begindate] <date_in_ISO_format>` filters transactions that are older than `<date_in_ISO_format>`
- `[-e | --enddate] <date_in_ISO_format>` filters transactions that are newer than `<date_in_ISO_format>`
- `[-n | --nodelete]` will not consider any removed transactions
