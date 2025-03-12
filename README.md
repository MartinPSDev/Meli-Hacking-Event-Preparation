# Meli-Hacking-Event-Preparation
Analysis of the Mercado Libre/Mercado Pago API with a focus on Bug Bounty. The aim is to conduct a study of the documentation to create a good surface from which to begin the search for bugs.

## Getting API key
Before starting we must go to the site https://developers.mercadolibre.com  and register an application to obtain an API key. Without this, all requests will give us a forbidden or unauthorized response.

## Official Documented Endpoints
These are the endpoints found in the documentation. We'll then try to find hidden endpoints.
### Mercado Libre:
```
/users/$USER_ID
/users/me
/users/$USER_ID/addresses
/users/$USER_ID/accepted_payment_methods
/applications/$APPLICATION_ID
/users/$USER_ID/brands
/users/$USER_ID/classifieds_promotion_packs
/users/$USER_ID/classifieds_promotion_packs/$LISTING_TYPE&categoryId=$CATEGORY_ID
/users/$USER_ID/available_listing_types?category_id=$CATEGORY_ID
/users/$USER_ID/available_listing_type/$LISTING_TYPE_ID?category_id=$CATEGORY_ID
/users/$USER_ID/applications/$APPLICATION_ID
/missed_feeds?app_id=$APP_ID
/sites
/sites/$SITE_ID/listing_types
/sites/$SITE_ID/listing_prices?price=$PRICE
/sites/$SITE_ID/categories
/categories/$CATEGORY_ID
/categories/$CATEGORY_ID/attributes
/sites/$SITE_ID/domain_discovery/search?q=$Q
/categories/$CATEGORY_ID/classifieds_promotion_packs
/domains/$DOMAIN_ID/technical_specs
/classified_locations/countries *
/classified_locations/countries/$COUNTRY_ID *
/classified_locations/states/$STATE_ID *
/classified_locations/cities/$CITY_ID *
/currencies
/currencies/$CURRENCY_ID
/currency_conversions/search?from=$CURRENCY_ID&to=$CURRENCY_ID
/countries/$COUNTRY_ID/zip_codes/$ZIP_CODE
/country/$COUNTRY_ID/zip_codes/search_between?zip_code_from=$ZIP_CODE_FROM&zip_code_to=$ZIP_CODE_TO
```

