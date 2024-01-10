# Realsoft API

https://admin.realsoft.sk/api/export


# Nastavenia pre ACF plugin 

v prípade custom webu, inak je to dané použitým pluginom alebo témou

## Makléri

V prípade importu: 

- ak to nie je pripravené vopred sa použije verzia user a je na tvorcovi webu, aby si s tým poradil (môže to ignorovať)

- v prípade väčšiny hotových Real Estate riešení je toto už vyriešené a dané (robí sa custom import)

- v prípade custom webu by to malo byť zapracované vopred pre importom. Ak to nie je ani po upozornení, použije sa free verzia pre import (user)

Poznámka:
- vo free verzii user sa páruje podľa emailu, nie ID

Testovacie údaje:
- vzor z dokumentácie
- reálne posielané údaje

## Taxonómie 

Číselníky z externého zdroja, údaje nie sú súčasťou exportu

## Typ nehnuteľností

(action podľa RS: Predaj, Prenájom...) 

Základné riešenie:

- taxonómia property_status prekladá sa ako transakcia alebo typ ak type je druh (nonsens) - houzez
- taxonómia property_action_category (wpresidence)
- taxonómia property_status (propertya)
- taxonómia property-status (essential real estate)

Lepší preklad: účel (wre pro plugin)

Iné riešenie: 
- custom field s definovanými možnosťami (wpcasa)


## Lokality

Realsoft má 4 úrovne lokalít: štát, kraj, okres, mesto (prípadne mestská časť), do exportu idú len IDčka. 

Základné riešenie:

- hierarchická taxonómia property_location (houzez)
- hierarchická taxonómia location  (wpcasa)  
- hierarchická taxonómia property_location (propertya)

Neštandardné riešenie (ála Houzez):

- 4 taxonómie: property_country (štát), property_state (kraj), property_city (okres), property_area (mesto)
- prepojenie je pomocou custom fields

Iné riešenie:

- údaje o lokalite sú custom fields, bez hierarchie... (wre pro plugin)
- nezávislé taxonómie: property_city a property_county_state (wpresidence)
- prepojené taxonómie: property_city a property_area (wpresidence)
- bez lokalít, len adresa (estatik)
- property-state (Province / State) (essential real estate) 
- property-city prepojené Country, Province / State (essential real estate) + property-neighborhood

Potrebujete prevodový číselník, viď: https://pixeler.sk/prepojenie-systemu-realsoft-s-wordpress-webstrankou





## Kategórie nehnuteľností  / Druh

(kategória je označenie z RS, dosť sa to pletie, v EN je to type, na toprealitách druh)

Základné riešenie:

- hierarchická taxonómia property_type (houzez)
- hierarchická taxonómia product_cat (woo)
- hierarchická taxonómia listing-type (wpcasa) listing-category je niečo iné
- hierarchická taxonómia property_category (wpresidence)
- hierarchická taxonómia property_type (propertya)
- hierarchická taxonómia property-type (essential real estate)

Iné riešenie:

- údaje o type sú custom fields, bez hierarchie... 
 

## Vlastnosti 

- taxonómia property_feature (houzez)
- taxonómia feature (wpcasa) 
- ??? product_tag (woo)
- taxonómia property_features (wpresidence) 
- taxonómia property_feature (propertya) 
- taxonómia property-feature (essential real estate) 

 
## Štítky a stav

- taxonómia property_label
- taxonómia listing_label 
- taxonómia property_status (wpresidence) 
- taxonómia property_label (propertya)  
- taxonómia property-label (essential real estate) 
 


## Identifikácia ponuky

vždy rs_id + rs_object_id

product:  rs_object_id = SKU (ak nie je špecifikované inak)

## Identifikácia taxonómie

pri woo cez ACF rs_id + rs_key + rs_term
- product_cat
- property_location









 
