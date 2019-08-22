---
title: API Reference

language_tabs:
  - json

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>


includes:
  - errors

search: true
---

# Introduction

Welcome to the QURAN API! You can use our API to access QURAN API endpoints, which can provide you with quranic surahs, ayahs, edition etc in our database.

# QURAN

## Get Quran
This endpoint retrieves whole quran in arabic.

### HTTP Request

`GET https://alquran.com/api/v1/get_quran`

> The response returns from the endpoint will be in JSON structured like this:

```json
[
  {
    "credit": 183.5
  }
]
```

## Get Quran Editions
This endpoint retrieves translations or tafsir or audio parah wise / surah wise of whole quran.

### HTTP Request

`GET https://alquran.com/api/v1/get_quran_editions`


> The response returns from the endpoint will be in JSON structured like this:

```json
[
  {
    "credit": 183.5
  }
]
```

# PARAH

## Get Parah
This endpoint retrieves the whole parah in arabic.

### HTTP Request

`GET https://alquran.com/api/v1/get_parah/:parah_no`

### URL Parameters

Parameter | Description
--------- | -----------
:parah_no | Parah number required

> The response returns from the endpoint will be in JSON structured like this:

```json
[
  {
    "credit": 183.5
  }
]
```

## Get Parah Editions

This endpoint retrieves the editions of parah.

### HTTP Request

`GET https://alquran.com/api/v1/get_parah_editions/:parah_no`

### URL Parameters

Parameter | Description
--------- | -----------
:parah_no | Parah number required

> The response returns from the endpoint will be in JSON structured like this:

```json
[
  {
    "credit": 183.5
  }
]
```

## Get Parahs with Sajood

This endpoint retrieves all the parahs in arabic which requires sajda.

### HTTP Request

`GET https://alquran.com/api/v1/get_sajood_parahs`


> The response returns from the endpoint will be in JSON structured like this:

```json
[
  {
    "credit": 183.5
  }
]
```

# SURAHS

## Get All Surahs
This endpoint retrieves all surahs in their respective orders.

### HTTP Request

`GET https://alquran.com/api/v1/get_surahs`


> The response returns from the endpoint will be in JSON structured like this:

```json
[
  {
    "credit": 183.5
  }
]
```

## Get Surah
This endpoint retrieves a particular surah in arabic.

### HTTP Request

`GET https://alquran.com/api/v1/get_surah/:surah_no` <br>
`GET https://alquran.com/api/v1/get_surah/:surah_name`

### URL Parameters

Parameter | Description
--------- | -----------
:surah_no | Surah number required
:surah_name | Surah name required

> The response returns from the endpoint will be in JSON structured like this:

```json
[
  {
    "credit": 183.5
  }
]
```

## Get Surah Editions
This endpoint retrieves a particular surah's editions.

### HTTP Request

`GET https://alquran.com/api/v1/get_surah_editions/:surah_no` <br>
`GET https://alquran.com/api/v1/get_surah_editions/:surah_name`

### URL Parameters

Parameter | Description
--------- | -----------
:surah_no | Surah number required
:surah_name | Surah name required

> The response returns from the endpoint will be in JSON structured like this:

```json
[
  {
    "credit": 183.5
  }
]
```


## Get Mecca Surahs
This endpoint retrieves all mecca surahs in arabic.

### HTTP Request

`GET https://alquran.com/api/v1/get_mecca_surahs`

> The response returns from the endpoint will be in JSON structured like this:

```json
[
  {
    "credit": 183.5
  }
]
```

## Get Madni Surahs
This endpoint retrieves all madni surahs in arabic.

### HTTP Request

`GET https://alquran.com/api/v1/get_madni_surahs`

> The response returns from the endpoint will be in JSON structured like this:

```json
[
  {
    "credit": 183.5
  }
]
```

## Get All Surahs with Sajood
This endpoint retrieves all surahs in arabic which requires sajda.

### HTTP Request

`GET https://alquran.com/api/v1/get_sajood_surahs`

> The response returns from the endpoint will be in JSON structured like this:

```json
[
  {
    "credit": 183.5
  }
]
```

## Get Particular Mecca Surah
This endpoint retrieves a particular surah from mecca surahs.

### HTTP Request

`GET https://alquran.com/api/v1/get_mecca_surah/:surah_no`

### URL Parameters

Parameter | Description
--------- | -----------
:surah_no | Surah number required

> The response returns from the endpoint will be in JSON structured like this:

```json
[
  {
    "credit": 183.5
  }
]
```

## Get Particular Madni Surah
This endpoint retrieves a particular surah from madni surahs.

### HTTP Request

`GET https://alquran.com/api/v1/get_madni_surah/:surah_no`

### URL Parameters

Parameter | Description
--------- | -----------
:surah_no | Surah number required

> The response returns from the endpoint will be in JSON structured like this:

```json
[
  {
    "credit": 183.5
  }
]
```

# AYAHS

## Get Sajda Ayahs
This endpoint retrieves all ayahs which require sajda.

### HTTP Request

`GET https://alquran.com/api/v1/get_sajda_ayahs`

> The response returns from the endpoint will be in JSON structured like this:

```json
[
  {
    "credit": 183.5
  }
]
```

## Get Ayahs
getAyas(surah_name, ayah_no, limit)
This endpoint retrieves all ayahs depending upons params.

### HTTP Request

`GET https://alquran.com/api/v1/get_ayahs`

> The response returns from the endpoint will be in JSON structured like this:

```json
[
  {
    "credit": 183.5
  }
]
```

## Get Ayah
This endpoint retrieves ayah depending upons params.

### HTTP Request

`GET https://alquran.com/api/v1/get_ayahs/:surah_no/:ayah_no`

### URL Parameters

Parameter | Description
--------- | -----------
:surah_no | Surah number required
:ayah_no | Ayah number required

> The response returns from the endpoint will be in JSON structured like this:

```json
[
  {
    "credit": 183.5
  }
]
```

## Get Ayah Editions
This endpoint retrieves all editions of required ayah(s) depending upons params.

### HTTP Request

`GET https://alquran.com/api/v1/get_ayahs_edition/:surah_no/:ayah_no`

Parameter | Description
--------- | -----------
:surah_no | Surah number required
:ayah_no | Ayah number required

> The response returns from the endpoint will be in JSON structured like this:

```json
[
  {
    "credit": 183.5
  }
]
```

# RUKU

## GET Ruku
This endpoint retrieves required ruku.

### HTTP Request

`GET https://alquran.com/api/v1/get_ruku/:ruko_no`

Parameter | Description
--------- | -----------
:ruku_no | Ruku number required

> The response returns from the endpoint will be in JSON structured like this:

```json
[
  {
    "credit": 183.5
  }
]
```

## GET Ruku Editions
This endpoint retrieves required ruku's editions.

### HTTP Request

`GET https://alquran.com/api/v1/get_ruku/:ruko_no/editions`

Parameter | Description
--------- | -----------
:ruku_no | Ruku number required


> The response returns from the endpoint will be in JSON structured like this:

```json
[
  {
    "credit": 183.5
  }
]
```

## Get All Rukus
This endpoint retrieves all rukus.

### HTTP Request

`GET https://alquran.com/api/v1/get_rukus`

> The response returns from the endpoint will be in JSON structured like this:

```json
[
  {
    "credit": 183.5
  }
]
```

# MANZIL

## Get Manzil
This endpoint retrieves manzil depending upons param.

### HTTP Request

`GET https://alquran.com/api/v1/get_manzil/:manzil_no`

Parameter | Description
--------- | -----------
:manzil_no | Manzil number required


> The response returns from the endpoint will be in JSON structured like this:

```json
[
  {
    "credit": 183.5
  }
]
```

## Get Manzil Editions
This endpoint retrieves manzil's editions depending upons param.

### HTTP Request

`GET https://alquran.com/api/v1/get_manzil/:manzil_no`

Parameter | Description
--------- | -----------
:manzil_no | Manzil number required


> The response returns from the endpoint will be in JSON structured like this:

```json
[
  {
    "credit": 183.5
  }
]
```

## Get All Manzils
This endpoint retrieves all manzils in arabic.

### HTTP Request

`GET https://alquran.com/api/v1/get_manzils`

> The response returns from the endpoint will be in JSON structured like this:

```json
[
  {
    "credit": 183.5
  }
]
```

# SEARCH

## Get Search Results
This endpoint retrieves all references / results that matches the searched query in editions.

### HTTP Request

`GET https://alquran.com/api/v1/get_references/:query`

> The response returns from the endpoint will be in JSON structured like this:

```json
[
  {
    "credit": 183.5
  }
]
```
