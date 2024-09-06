---
layout: default
title: Email
parent: Types
grand_parent: Data Generation
has_children: false
nav_order: 1
---

# Email

Returns a fake email using a dictionary of names that can be filtered on country and randomly . or numbers and an @ with a provider between: gaagle.com, yahaa.com, uutlook.com, email.fr.


## Parameters

Possible parameters for this type are:

- **possible_values**: an array of possible values
- **filters**: an array to filter on country for names generated inside the email
- **ghost**: To compute this field but does not output it. (This is useful foor generating more complex fields using one or multiple ghost fields)


## Examples

A random email:

```json
    {
      "name": "userEmail",
      "type": "EMAIL"
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

