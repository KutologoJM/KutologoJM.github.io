---
title: Oni Recipes API - Ingredients
author: KutologoJM
description: Ingredients Description
categories: [api-endpoint]
tags: [api]
permalink: /oni-recipes-api/ingredients/
---

# Ingredients Model
## Fields:

- name
    - The name of the ingredient.
    - This field is required.
- description
    - A short description of the ingredient.
- slug
    - A url friendly version of the ingredient name.
    - Read-only
    - Auto-generated
- dlc
    - Which dlc if any this ingredient belongs to.
    - This field is required.
- ingredient_image_url
    - An external link to a picture of the chosen ingredient.
- spoil_time
    - The time in no. of cycles, the ingredient can last before spoiling.
    - This field is required.
- food_quality
    - This field is required.
    - The given ingredient's quality and morale impact.
    - Given in the form:
  ```python
  {"Quality": "Standard", "Morale impact": "+2"}
  ```
- kcal_per_kg
    - The amount of kilocalories per kilogram the ingredient contains.
    - This field is required.
- source
    - The item, place or animal this ingredient can be obtained from in game.
    - This field is required.
- source_image_url
    - An external link to a picture of the ingredient's source

### GET Method
```python
GET <api>/ingredients/1/
# This will allow you to view a specific ingredient based on its ID.

GET <api>/ingredients/
# This will display all ingredients currently saved within the model.

GET <api>/ingredients/?ordering=<field_name>
# This will allow you to sort all the ingredient by your desired field.
example field names:
    - slug
    - names
    - spoil_time
ascending: field_name
descending: -field_name
```

```python
GET <api>/ingredients/1/
{
    "name": "Frost Bun",
    "description": "A simple bun baked from Sleet Wheat Grain.\r\nEach bite leaves a mild cooling sensation in one's mouth, even when the bun itself is warm.",
    "slug": "frost-bun",
    "dlc": "Base",
    "ingredient_image_url": "https://oxygennotincluded.wiki.gg/images/Resource_Frost_Bun.png?91f368=&format=original",
    "spoil_time": 8,
    "food_quality": {
        "Quality": "Standard",
        "Morale impact": "+2"
    },
    "kcal_per_kg": 1200,
    "source": "Electric Grill",
    "source_image_url": "https://oxygennotincluded.wiki.gg/images/9/97/Electric_Grill.png?7e3bb5=&format=original"
}
```


### POST Method
```python
#  Allows you to create a new ingredient.
POST {
  "name": "",
  "description": "",
  "ingredient_image_url": "",
  "dlc": "",
  "food_quality":,
  "spoil_time": ,
  "kcal_per_kg": ,
  "source": "",
  "source_image_url": ""
}

```

```python
# An example of a ingredient being added, in this case the "Frost Bun".
POST {
    "name": "Frost Bun",
    "description": "A simple bun baked from Sleet Wheat Grain.\r\nEach bite leaves a mild cooling sensation in one's mouth, even when the bun itself is warm.",
    "dlc": "Base",
    "ingredient_image_url": "https://oxygennotincluded.wiki.gg/images/Resource_Frost_Bun.png?91f368=&format=original",
    "spoil_time": 8,
    "food_quality": {
        "Quality": "Standard",
        "Morale impact": "+2"
    },
    "kcal_per_kg": 1200,
    "source": "Electric Grill",
    "source_image_url": "https://oxygennotincluded.wiki.gg/images/9/97/Electric_Grill.png?7e3bb5=&format=original"
}
```

### PATCH / PUT Method
```python
# Allows you to modify a part or all of a given ingredient
PATCH / PUT <api>/ingredients/1/
{
    "name": "",
    "description": "",
    "ingredient_image_url": "",
    "dlc": "",
    "food_quality":,
"spoil_time": ,
"kcal_per_kg": ,
"source": "",
"source_image_url": ""
}

```
```python
# An example patch changing the ingredient with id 3's dlc from Base to PPP!.
PATCH / PUT <api>/ingredient/3/
{
    "name": "Frost Bun",
    "description": "A simple bun baked from Sleet Wheat Grain.\r\nEach bite leaves a mild cooling sensation in one's mouth, even when the bun itself is warm.",
    "dlc": "PPP!",
    "ingredient_image_url": "https://oxygennotincluded.wiki.gg/images/Resource_Frost_Bun.png?91f368=&format=original",
    "spoil_time": 8,
    "food_quality": {
        "Quality": "Standard",
        "Morale impact": "+2"
    },
    "kcal_per_kg": 1200,
    "source": "Electric Grill",
    "source_image_url": "https://oxygennotincluded.wiki.gg/images/9/97/Electric_Grill.png?7e3bb5=&format=original"
}
```

### DELETE Method
```python
DELETE <api>/ingredients/1/
# Deletes the ingredient with the given ID.
```