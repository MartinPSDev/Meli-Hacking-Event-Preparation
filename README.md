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
/sites/$SITE_ID/search?category=$CATEGORY_ID
/sites/$SITE_ID/search?q=Motorola%20G6
/sites/$SITE_ID/search?nickname=$NICKNAME
/sites/$SITE_ID/search?seller_id=$SELLER_ID
/sites/$SITE_ID/search?seller_id=$SELLER_ID&category=$CATEGORY_ID
/users/$USER_ID/items/search
/items?ids=$ITEM_ID1,$ITEM_ID2
/users?ids=$USER_ID1,$USER_ID2
/items?ids=$ITEM_ID1,$ITEM_ID2&attributes=$ATTRIBUTE1,$ATTRIBUTE2,$ATTRIBUTE3
/users/$USER_ID/items/search?search_type=scan
/questions/search?item=$ITEM_ID
/questions
/answers
/questions/$QUESTION_ID
/block-api/search/users/$USER_ID
/users/$SELLER_ID/questions_blacklist/$BUYER_ID
/my/received_questions/search
/orders/search?seller=$SELLER_ID
/orders/search?seller=$SELLER_ID&q=$ORDER_ID
/orders/search?buyer=$BUYER_ID
/sites/$SITE_ID/payment_methods
/sites/$SITE_ID/payment_methods/$id
/orders/$ORDER_ID/feedback
/feedback/$FEEDBACK_ID
/feedback/$FEEDBACK_ID/reply
/block-api/search/users/$USER_ID
/users/$SELLER_ID/order_blacklist
/orders/$ORDER_ID/product
/users/$USER_ID/items_visits?date_from=$DATE_FROM&date_to=$DATE_TO
/users/$USER_ID/items_visits/time_window?last=$LAST&UNIT=$UNIT&ENDING=$ENDING
/users/$USER_ID/contacts/questions?date_from=$DATE_FROM&date_to=$DATE_TO
/users/$USER_ID/contacts/questions/time_window?last=$LAST&UNIT=$UNIT
/users/$USER_ID/contacts/phone_views?date_from=$DATE_FROM&DATE_TO=$DATE_TO
/users/$USER_ID/contacts/phone_views/time_window?last=$LAST&UNIT=$UNIT
/items/visits?ids=$ID1, ID2&date_from=$DATE_FROM&date_to=$DATE_TO
/items/$ITEM_ID/visits/time_window?last=$LAST&UNIT=$UNIT&ENDING=$ENDING
/items/visits/time_window?ids=$ID1, ID2last=$LAST&UNIT=UNIT&ENDING=$ENDING
/items/contacts/phone_views/time_window?ids=$ID1,ID2&last=$LAST&UNIT=$UNIT&ENDING=ENDING_DATE
/shipments/$SHIPMENT_ID
/items/$ITEM_ID/shipping_options
/sites/$SITE_ID/shipping_methods
/users/$CUST_ID/shipping_preferences
/orders/$ORDER_ID/shipments
/shipment_labels
/shipment_labels?shipment_ids=$SHIPMENT_ID&response_type=zpl2
/shipment_labels?shipment_ids=$SHIPMENT_ID&savePdf=Y
```

