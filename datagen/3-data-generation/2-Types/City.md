---
layout: default
title: City
parent: Types
grand_parent: Data Generation
has_children: false
nav_order: 1
---

# City

A city taken from a dictionnary of 40K+ cities over the world with associated latitude, longitude and country.

It can be filtered by country.

The field city offers a link to its latitude, longitude and country, available to use by another field.

_Note: Cities occurences are weighted by their population, rendering more coherent results_


## Parameters

Possible parameters for this type are:

- **filters**: an array of countries to filter the cities taken from.
- **ghost**: To compute this field but does not output it. (This is useful foor generating more complex fields using one or multiple ghost fields)


## Examples

A random city across the world:

```json
{
  "name": "city",
  "type": "CITY"
}
```

A city located in USA:

```json
{
  "name": "city_in_usa",
  "type": "CITY",
  "filters": ["USA"]
}
```


This below example creates 4 fields: 

- City name (located in France or Spain)
- Latitude of this city (available as lat)
- Longitude of this city (available as long)
- Country where this city is (available as country)

```json
{
  "name": "city",
  "type": "CITY",
  "filters": ["France", "Spain"]
},
{
  "name": "city_lat",
  "type": "LINK",
  "conditionals": {
    "link": "$city.lat"
  }
},
{
  "name": "city_long",
  "type": "LINK",
  "conditionals": {
    "link": "$city.long"
  }
},
{
  "name": "city_country",
  "type": "LINK",
  "conditionals": {
    "link": "$city.country"
  }
}
```

## Countries Available

Full available list of countries: 

Afghanistan
Albania
Algeria
American Samoa
Andorra
Angola
Anguilla
Antigua And Barbuda
Argentina
Armenia
Aruba
Australia
Austria
Azerbaijan
Bahrain
Bangladesh
Barbados
Belarus
Belgium
Belize
Benin
Bermuda
Bhutan
Bolivia
Bosnia And Herzegovina
Botswana
Brazil
British Virgin Islands
Brunei
Bulgaria
Burkina Faso
Burundi
Cabo Verde
Cambodia
Cameroon
Canada
Cayman Islands
Central African Republic
Chad
Chile
China
Christmas Island
Colombia
Comoros
Congo (Brazzaville)
Congo (Kinshasa)
Cook Islands
Costa Rica
Croatia
Cuba
Curaçao
Cyprus
Czechia
Côte d'Ivoire
Denmark
Djibouti
Dominica
Dominican Republic
Ecuador
Egypt
El Salvador
Equatorial Guinea
Eritrea
Estonia
Ethiopia
Falkland Islands (Islas Malvinas)
Faroe Islands
Federated States of Micronesia
Fiji
Finland
France
French Guiana
French Polynesia
Gabon
Gaza Strip
Georgia
Germany
Ghana
Gibraltar
Greece
Greenland
Grenada
Guadeloupe
Guam
Guatemala
Guinea
Guinea-Bissau
Guyana
Haiti
Honduras
Hong Kong
Hungary
Iceland
India
Indonesia
Iran
Iraq
Ireland
Isle Of Man
Israel
Italy
Jamaica
Japan
Jersey
Jordan
Kazakhstan
Kenya
Kiribati
Kosovo
Kuwait
Kyrgyzstan
Laos
Latvia
Lebanon
Lesotho
Liberia
Libya
Liechtenstein
Lithuania
Luxembourg
Macau
Macedonia
Madagascar
Malawi
Malaysia
Maldives
Mali
Malta
Marshall Islands
Martinique
Mauritania
Mauritius
Mayotte
Mexico
Moldova
Monaco
Mongolia
Montenegro
Montserrat
Morocco
Mozambique
Myanmar
Namibia
Nauru
Nepal
Netherlands
New Caledonia
New Zealand
Nicaragua
Niger
Nigeria
Niue
Norfolk Island
North Korea
Northern Mariana Islands
Norway
Oman
Pakistan
Palau
Panama
Papua New Guinea
Paraguay
Peru
Philippines
Pitcairn Islands
Poland
Portugal
Puerto Rico
Qatar
Reunion
Romania
Russia
Rwanda
Saint Barthelemy
Saint Helena  Ascension  And Tristan Da Cunha
Saint Kitts And Nevis
Saint Lucia
Saint Martin
Saint Pierre And Miquelon
Saint Vincent And The Grenadines
Samoa
San Marino
Sao Tome And Principe
Saudi Arabia
Senegal
Serbia
Seychelles
Sierra Leone
Singapore
Sint Maarten
Slovakia
Slovenia
Solomon Islands
Somalia
South Africa
South Georgia And South Sandwich Islands
South Korea
South Sudan
Spain
Sri Lanka
Sudan
Suriname
Svalbard
Swaziland
Sweden
Switzerland
Syria
Taiwan
Tajikistan
Tanzania
Thailand
The Bahamas
The Gambia
Timor-Leste
Togo
Tonga
Trinidad And Tobago
Tunisia
Turkey
Turkmenistan
Turks And Caicos Islands
Tuvalu
U.S. Virgin Islands
UK
USA
Uganda
Ukraine
United Arab Emirates
Uruguay
Uzbekistan
Vanuatu
Vatican City
Venezuela
Vietnam
Wallis And Futuna
West Bank
Yemen
Zambia
Zimbabwe