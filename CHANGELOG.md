# Changelog

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
