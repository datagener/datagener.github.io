---
layout: default
title: Name
parent: Types
grand_parent: Usage
has_children: false
nav_order: 1
---

# Name

A name taken from a dictionnary of over 20K+ names classed by country and occurence in that country.

It can be filtered out by country.

_Note: To make it more accurate, names are taken according to their occurences in the country_


## Parameters

Possible parameters for this type are:

- **Filters**: To filter on or multiple countries

## Use City's in other fields

If a column is of type Name, and its name is `my_name`, one can use another column as LINK type and get:

- sex associated to the name with (MALE/FEMALE/UNKNOWN): `$my_city.sex`
- if sex associated to the name is considered as male with: `$my_city.male`
- if sex associated to the name is considered as female with: `$my_city.female`
- if sex associated to the name is considered as uni-sex with: `$my_city.unisex`


## List of available countries

Full list of available countries:

Albania
Algeria
Arabia
Armenia
Austria
Azerbaijan
Belarus
Belgium
Bosnia and Herzegovina
Bulgaria
China
Croatia
Czech Republic
Denmark
Estonia
Finland
France
Georgia
Germany
Greece
Hungary
Iceland
India
Ireland
Israel
Italy
Japan
Kazakhstan
Korea
Kosovo
Latvia
Lithuania
Luxembourg
Macedonia
Moldova
Montenegro
Morocco
Netherlands
Norway
Poland
Portugal
Romania
Russia
Serbia
Slovakia
Slovenia
Spain
Sweden
Switzerland
Tunisia
Turkey
UK
USA
Ukraine
Vietnam
