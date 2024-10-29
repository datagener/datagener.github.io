---
layout: default
title: Name
parent: Types
grand_parent: Usage - API
has_children: false
nav_order: 1
---

# Name

A name taken from a dictionnary of over 20K+ names classed by country and occurence in that country.

It can be filtered out by country.

_Note: To make it more accurate, names are taken according to their occurences in the country_


## Parameters


Possible parameters for this type are:

- **filters**: an array of countries to filter the names taken from.
- **ghost**: To compute this field but does not output it. (This is useful foor generating more complex fields using one or multiple ghost fields)


## Examples

A name:

```json
    {
      "name": "name",
      "type": "NAME"
    }
```

A French name:

```json
    {
      "name": "french_name",
      "type": "NAME",
      "filters": ["France"]
    }
```

A UK or US name:
```json
    {
      "name": "us_uk_name",
      "type": "NAME",
      "filters": ["USA", "UK"]
    }
```

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
