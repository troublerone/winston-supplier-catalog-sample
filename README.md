# Supplier CSV to WooCommerce: worked example — USD 9 minimum

For ecommerce implementers preparing one documented supplier CSV, this example
shows the input, explicit mapping, draft import, row audit, and refused row.
The input is synthetic. It establishes neither customer demand nor a successful
live-store import. Inspect these files without paying for a run.

## Inspect the complete example

- [Supplier input](worked-example/supplier-input.csv): seven data rows.
- [Declared mapping](worked-example/mapping.json): parent token, column names,
  case suffix, size/color synonyms, and inventory units.
- [WooCommerce draft](worked-example/woocommerce-corrected.csv): seven output
  rows, including a generated parent, five variations, and a simple product.
- [Source map](worked-example/source-to-output-mapping.csv): decisions for all
  seven source rows, including the refusal.
- [Exceptions](worked-example/exceptions.csv): one row requiring correction.
- [Manifest](worked-example/manifest.json): counts, hashes, and provenance.

Rows 1–5 share the declared H300 parent. Size and color labels are normalized.
Row 6 removes the declared -CASE suffix and converts two six-unit cases into
12 eaches. Row 7 has an ambiguous parent key and missing case size; it is excluded
with PARENT_KEY_AMBIGUOUS and CASE_SIZE_IS_MISSING. The tool does not guess.
The draft uses Published=-1; review it before a controlled import.

These files were reproduced locally from the acceptance input and mapping. All
three output SHA-256 hashes match the recorded private unmonetized Apify run
IN2YgSVfSdMGdT9Vc, build eibI26ZTs322kUuSy (2026-09-09). That run resolved six
source rows and refused one. Its charge state was NOT_APPLICABLE. The cloud run
could not be retrieved in this documentation session (HTTP 403). The manifest
here is a local provenance record, not a retrieved cloud billing receipt.
Public paid charging acceptance remains UNKNOWN.

## Run route and effective price

[Open the Actor and its run form](https://apify.com/winstonvale/supplier-csv-to-woocommerce-variations).
Sign in to Apify to configure a run. Upload your CSV using the supplierCsv file
input and supply the explicit mapping shown above; maxRows may be at most 10000.
For this synthetic example, the complete [Actor input](worked-example/actor-input.json)
uses the existing public acceptance upload URL. That URL may expire; upload
supplier-input.csv yourself if unavailable. Do not place customer data in GitHub.
Review the current price and maximum-charge setting before starting.

Public Actor metadata checked 2026-09-09 reports a USD 9 minimum total-charge
limit: USD 0.005 per Actor-start event plus USD 8.995 for one completed bundle.
The platform defines start events by allocated GB, minimum one event. Thus USD 9
is the complete-bundle price with one start event; larger memory allocations can
increase it. A fatal validation failure can still incur the start event. An
exception-bearing completed bundle is chargeable. Local product documentation
states there is no dataset-item charge and platform usage is included.
This documentation session started no Actor and incurred no Actor charges.

After a completed run, download the three named CSVs from default storage and
inspect OUTPUT and the dataset manifest. Compare hashes, resolve exceptions,
then review the draft in your controlled WooCommerce import workflow. The Actor
does not access or modify your store. If chargeState is ambiguous, or a confirmed
charge is followed by an incomplete OUTPUT, reconcile platform charge records
before retrying. A missing summary is not permission to pay again.

## Limits

One UTF-8 comma-delimited CSV, one declared mapping, at most 10 MiB and 10,000 data
rows. Missing parents/case sizes, duplicate identities, unsupported units, and
unsafe spreadsheet formulas are held back as explicit exceptions; fatal schema
or unsafe-regex errors refuse conversion. No live import, store repair, OCR,
enrichment, image download, currency conversion, or recurring synchronization.
Stored file URLs are data-bearing links, not a confidentiality guarantee;
download promptly and check your storage access and retention settings.
