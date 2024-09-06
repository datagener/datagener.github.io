---
layout: default
title: Swagger & API
parent: Basic
grand_parent: Data Generation
has_children: true
nav_order: 1
---

# Using Swagger

Go to Swagger-UI.

Select **data-generation-controller** and then **/datagen/csv** endpoint, there are few parameters to fill-in:

- _batches_: **1**
- _rows_: **10**
- _threads_: **1**
- _model_: **models/customer/customer-france-model.json**

Click on "execute" and then check the result that should be outputed in file: _/home/datagen/customer/customer-fr-0000000000.csv_:

```shell
name,id,birthdate,city,country,email,phone_number,membership
"Brigitte","120001","30/07/1987","Neuilly-Plaisance","France","Brigitte@company.fr","+33 576366805","BRONZE"
"Sonia","120002","18/07/1982","Perpignan","France","Sonia@company.fr","+33 254004334","SILVER"
"Olivier","120003","26/05/1973","Plerin","France","Olivier@company.fr","+33 008768115","SILVER"
"Guillaume","120004","19/01/1971","Nice","France","Guillaume@company.fr","+33 113548479","SILVER"
"Benjamin","120005","02/08/1973","Paris","France","Benjamin@company.fr","+33 729420702","BRONZE"
"Corinne","120006","21/11/1997","Flines-les-Raches","France","Corinne@company.fr","+33 448940553","PLATINUM"
"Annick","120007","01/04/1990","Paris","France","Annick@company.fr","+33 740608106","BRONZE"
"Ludovic","120008","19/04/1965","Toulouse","France","Ludovic@company.fr","+33 215503877","BRONZE"
"Anne","120009","08/10/1960","Paris","France","Anne@company.fr","+33 058134557","GOLD"
"Gilles","120010","06/08/1958","La Garde","France","Gilles@company.fr","+33 787202512","PLATINUM"
```

Here, model file has been given using a local path, but it is also posisble to directly provide the model (from your local computer) using the parameter **model_file** instead of model.


# Using API


In a terminal with curl tool installed and access to machine where Datagen is running, execute following curl command:

```shell
curl -X POST "http://<YOUR_DATAGEN_HOSTNAME>:4242/datagen/json" -H  "accept: */*" -H  "Content-Type: multipart/form-data" -F "batches=1" -F "model=models/customer/customer-france-model.json" -F "rows=10" -F "threads=1"
```

Result should be similar to above with, a file being created at _/home/datagen/customer/customer-fr-0000000000.json_:

```shell
{ "name" : "Pascale", "id" : "120001", "birthdate" : "1981-02-06", "city" : "La Motte-Servolex", "country" : "France", "email" : "Pascale@company.fr", "phone_number" : "+33 346750433", "membership" : "BRONZE" }
{ "name" : "Fabrice", "id" : "120002", "birthdate" : "1952-12-24", "city" : "Paris", "country" : "France", "email" : "Fabrice@company.fr", "phone_number" : "+33 278200587", "membership" : "BRONZE" }
{ "name" : "Serge", "id" : "120003", "birthdate" : "1973-11-02", "city" : "Lamballe", "country" : "France", "email" : "Serge@company.fr", "phone_number" : "+33 484525898", "membership" : "BRONZE" }
{ "name" : "Fabrice", "id" : "120004", "birthdate" : "1976-03-20", "city" : "Nogent-sur-Seine", "country" : "France", "email" : "Fabrice@company.fr", "phone_number" : "+33 066937739", "membership" : "BRONZE" }
{ "name" : "Karine", "id" : "120005", "birthdate" : "1963-07-09", "city" : "Rosny-sous-Bois", "country" : "France", "email" : "Karine@company.fr", "phone_number" : "+33 583230960", "membership" : "BRONZE" }
{ "name" : "Martial", "id" : "120006", "birthdate" : "2000-10-04", "city" : "Paris", "country" : "France", "email" : "Martial@company.fr", "phone_number" : "+33 658536142", "membership" : "BRONZE" }
{ "name" : "Vincent", "id" : "120007", "birthdate" : "1983-11-25", "city" : "Toulon", "country" : "France", "email" : "Vincent@company.fr", "phone_number" : "+33 638352763", "membership" : "GOLD" }
{ "name" : "Paul", "id" : "120008", "birthdate" : "1960-11-25", "city" : "Ville-la-Grand", "country" : "France", "email" : "Paul@company.fr", "phone_number" : "+33 270473971", "membership" : "SILVER" }
{ "name" : "Philippe", "id" : "120009", "birthdate" : "1971-10-14", "city" : "Brignoles", "country" : "France", "email" : "Philippe@company.fr", "phone_number" : "+33 934457223", "membership" : "BRONZE" }
{ "name" : "Jean", "id" : "120010", "birthdate" : "1979-04-10", "city" : "Le Barcares", "country" : "France", "email" : "Jean@company.fr", "phone_number" : "+33 738433840", "membership" : "BRONZE" }
```
