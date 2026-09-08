# Truthful synthetic sample

This sample is synthetic and contains no merchant or supplier data. It tests the
narrow problem evidenced by current public reports: a supplier file can lack
explicit parent rows, use inconsistent variant terms, and mix cases with eaches.

`supplier-input.csv` has seven source rows. The corrected file:

- groups the five `H300-*` rows under the explicit derived parent `H300`;
- normalizes `small`, `M`, `L`, `Large`, and `XL` to stable size terms;
- normalizes `EA`/`ea`/`Each` to eaches;
- converts two cases of six `H400` units to 12 eaches;
- publishes products as drafts (`Published=-1`), avoiding an accidental public
  listing if a user imports the sample;
- excludes row 7 because neither its parent model nor its case size is knowable.

`woocommerce-corrected.csv` uses the column contract in WooCommerce's official
Product CSV importer documentation. It is a demonstrable sample, not proof that
the transformation generalizes to arbitrary supplier files. A production offer
must require an explicit supplier-specific mapping profile and must preserve all
unmapped or ambiguous rows as exceptions.

Source basis:

- https://www.reddit.com/r/woocommerce/comments/1vth52w/woocommerces_variable_product_csv_structure_is/
- https://woocommerce.com/document/product-csv-importer-exporter/

