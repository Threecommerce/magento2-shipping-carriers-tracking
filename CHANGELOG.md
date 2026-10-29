# Changelog

## 1.3.1
- Fix: the REST response of a carrier just created by `POST` had empty `created_at` and `updated_at`.

## 1.3.0
- Created and Updated dates on every carrier: new columns in the grid (sortable, filterable by date range) and `created_at` / `updated_at` (UTC, read-only) in the REST API. Existing carriers get the date of the upgrade.

## 1.2.0
- Setting "Enabled" (Stores > Configuration > Threecommerce Plugins > Shipping Carriers, default Yes). With No Magento behaves as if the module were not installed: no custom carriers in the dropdown, no carrier links, no `tracking_url` in the shipments REST API. The carriers list and its REST API stay available.
- REST API: `POST /V1/threecommerce-shipping-carriers` creates a carrier or updates the one with the same code (fields you leave out keep their value), `DELETE /V1/threecommerce-shipping-carriers/:code` deletes it. Same validation as the admin.
- Grid: inline editing (name, tracking URL, active, sort order) and mass actions Enable / Disable / Delete.
- URL placeholders `{firstname}` and `{lastname}`; the `#TRACKNUM#`, `#POSTCODE#`, `#COUNTRYCODE#`, `#FIRSTNAME#` and `#LASTNAME#` forms are accepted too, so URLs from other tracking modules can be reused as they are.

## 1.1.0
- REST API: the final `tracking_url` of our carriers is in the `extension_attributes` of every track returned by `GET /V1/shipment/:id` and `GET /V1/shipments`.
- REST API: `GET /V1/threecommerce-shipping-carriers` and `GET /V1/threecommerce-shipping-carriers/:code` return the carriers list (code, title, tracking URL template, active, sort order). ACL resource: Shipping Carriers.
- Setting "Hide Standard Carriers" (Stores > Configuration > Threecommerce Plugins > Shipping Carriers): remove Magento's standard carriers (UPS, FedEx, DHL, USPS, Custom Value...) from the dropdown of "Add Tracking Number". Your own carriers are always listed.

## 1.0.2
- Fix: the carrier edit form stayed on an endless spinner (missing data provider, data scope and form template).

## 1.0.1
- Fix: the Action column of the carriers grid (Edit / Delete) was empty.

## 1.0.0
- Carriers managed in the admin (Sales > Operations > Shipping Carriers): name, code, tracking URL template, active, sort order.
- Active carriers appear in the carrier dropdown when adding a tracking number to a shipment.
- Tracking links in emails, order pages and admin point straight to the carrier's page.
- Nine common Italian carriers created inactive on install.
