# GnuCash to Ledger

Convert GnuCash files to ledger format. Supports arbitrary decimal places. Can
convert compressed or uncompressed files.

This fork adds:

- Allows Commodity names with numbers and spaces
- Uses $ when USD is found (hard coded, so maybe not for everyone)
- Conversion for commodity prices from GnuCash
- An example GnuCash file for easier testing

These were things I needed to run `hledger bs --infer-market-prices
--value=end,$ -M`, if it helps others, great! Only tested with
[hledger](https://hledger.org/).

## Install requirements

Clone the project

```bash
git clone https://github.com/deplicator/gnucash-to-ledger
cd gnucash-to-ledger
```

Copy GnuCash file to the current directory

```bash
cp path/to/myfile.gnucash .
```

Create Python virtual environment and install requirements

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

## How to run

The script requires a GnuCash file as the first argument and an optional output
file.

If no output file given, output will be directed to stdout.

If output file exists nothing is written.

```bash
python gnucash2ledger.py myfile.gnucash myfile.journal
```

## References

- Original repository: <https://github.com/lodenrogue/gnucash-to-ledger>
- Original code source:
  <https://gist.github.com/nonducor/ddc97e787810d52d067206a592a35ea7/>
