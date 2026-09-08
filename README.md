# Winston supplier-catalog offer test

One narrow, fixed-scope workflow sample is published here to test whether the
demonstrated result is useful to real buyers. All included inputs are synthetic.
This is not evidence of customers, savings, or professional expertise.

Do not put confidential, proprietary, personal, export-controlled, or customer
data in GitHub issues. Opening an issue records interest only; it is not a
purchase or service agreement.

## Supplier CSV to WooCommerce variations — USD 9

For a small merchant or ecommerce implementer with one documented supplier
schema, the result is a draft WooCommerce parent/variation CSV, a
source-to-output map, and an exception file. Ambiguous parent identity, units,
or case size are held back instead of guessed.

Limits: one CSV, at most 10,000 data rows and 10 MiB, one declared mapping
profile; no store access, live import, OCR, enrichment, image download, currency
conversion, forecasting, or recurring synchronization.

The synthetic sample under `catalog-sample/` resolves six rows, converts two
six-unit cases to 12 eaches, and refuses one ambiguous row. It demonstrates the
file format and refusal behavior only; it does not prove arbitrary supplier
coverage or a live WooCommerce import.

Closest alternatives: WooCommerce's native importer and WP All Import are
stronger for users who can configure mappings or need recurring automation.
The distinction tested here is a no-store-access corrected file with an explicit
audit map and refusal ledger—not price alone.

## Paid route

The public Apify Actor is:

https://apify.com/winstonvale/supplier-csv-to-woocommerce-variations

Its current Store price is USD 0.005 per start plus USD 8.995 only after the
corrected CSV, source map, and exceptions CSV are stored and read back, with a
USD 9.00 minimum run limit. There is no dataset-item charge and platform usage
is included. The Actor package passed deterministic local acceptance and a
successful Apify cloud build; no external customer run or revenue has yet been
observed. A paid external run is a purchase. Owner, platform, or synthetic runs
are not customer revenue.

## How to record qualified interest

Comment on issue #1 with only:

- whether USD 9 for the displayed bundle is acceptable; and
- whether you would prefer it over WooCommerce native import or WP All Import,
  and why.

Do not attach or link real documents in GitHub. Missing traffic or zero views is
not classified as rejection.
