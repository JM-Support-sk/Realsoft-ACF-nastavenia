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



## Lokality

Realsoft má 4 úrovne lokalít: štát, kraj, okres, mesto (prípadne mestská časť), do exportu idú len IDčka. 

Základné riešenie:

- hierarchická taxonómia property_location  (napĺňa sa importom ponúk)
- hierarchická taxonómia location  (ála wpcasa, napĺňa sa importom ponúk)  

Neštandardné riešenie (ála Houzez):

- 4 taxonómie: property_country (štát), property_state (kraj), property_city (okres), property_area (mesto)
- prepojenie je pomocou custom fields

Iné riešenie:

- údaje o lokalite sú custom fields, bez hierarchie... 

Potrebujete prevodový číselník, viď: https://pixeler.sk/prepojenie-systemu-realsoft-s-wordpress-webstrankou


## Typy nehnuteľností 

akcia... predaj, prenájom...  taxonomy

custom field


## Kategórie nehnuteľností 

Hierarchický číselník

- product_category priamo

- custom taxonomy

- týmto je daný počet izieb!!! 



## Identifikácia ponuky

vždy rs_id + rs_object_id

product:  rs_object_id = SKU (ak nie je špecifikované inak)







 
