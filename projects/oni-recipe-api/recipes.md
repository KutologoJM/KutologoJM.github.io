---
title: Oni Recipes API - Recipes
author: KutologoJM
description: Recipes Description
categories: [api-endpoint]
tags: [api]
permalink: /oni-recipes-api/recipes/
---

# Recipes Model
## Fields:

- name
    - The name of the recipe.
    - This field is required.
- description
    - A short description of the recipe.
- slug
    - A url friendly version of the recipe name.
    - Read-only
    - Auto-generated
- image_url
    - An external link to a picture of the chosen recipe.
- dlc
    - Which dlc if any this recipe belongs to.
    - This field is required.
- food_quality
    - This field is required.
    - The given recipe's quality and morale impact.
    - Given in the form:
  ```python
  {"Quality": "Standard", "Morale impact": "+2"}
  ```
- spoil_time
    - The time in no. of cycles, the recipe can last before spoiling.
    - This field is required.
- kcal_per_kg
    - The amount of kilocalories per kilogram the recipe contains.
    - This field is required.
- ingredients
    - a list of all the ingredients associated with the given recipe.
    - belongs to the Ingredients model with RecipeIngredients as a through model.
- source
    - The place this recipe can be obtained in game.
    - This field is required.
- source_image_url
    - An external link to a picture of the recipe's source.
- calories_produced
    - The number of kilocalories the recipe contains.
    - This field is required.

### GET Method
```python
GET <api>/recipes/1/
# This will allow you to view a specific recipe based on its ID.

GET <api>/recipes/
# This will display all recipes currently saved within the model.

GET <api>/recipes/?ordering=<field_name>
# This will allow you to sort all the recipes by your desired field.
example field names:
    - slug
    - names
    - spoil_time
ascending: field_name
descending: -field_name
```

> To view an example of what the GET method returns, please click [here.]({{ '/oni-recipes-api/test/' | base_url }})


### POST Method
```python
#  Allows you to create a new recipe.
POST {
  "name": "",
  "description": "",
  "image_url": "",
  "dlc": "",
  "food_quality":,
  "spoil_time": ,
  "kcal_per_kg": ,
  "source": "",
  "source_image_url": "",
  "calories_produced": 
}

```

```python
# An example of a recipe being added, in this case the "Frost Burger".
POST {
    "name": "Frost Burger",
    "description": "Meat and Lettuce on a chilled Frost Bun.\r\nIt's the only burger ever to be served cold.",
    "image_url": "https://oxygennotincluded.wiki.gg/images/Resource_Frost_Burger.png?5bef19&format=original",
    "dlc": "Base",
    "food_quality": {
        "Morale impact": "+6",
        "Quality": "Ambrosial"
    },
    "spoil_time": 4,
    "kcal_per_kg": 6000,
    "source": "Gas Range",
    "source_image_url": "https://oxygennotincluded.wiki.gg/images/Gas_Range.png?caa6a2=&format=original",
    "calories_produced": 6000
}
```

### PATCH / PUT Method
```python
# Allows you to modify a part or all of a given recipe
PATCH / PUT <api>/recipes/1/
{
  "name": "",
  "description": "",
  "image_url": "",
  "dlc": "",
  "food_quality":,
"spoil_time": ,
"kcal_per_kg": ,
"source": "",
"source_image_url": "",
"calories_produced":
}

```
```python
# An example patch changing the recipe with id 1's morale impact from 6 to 5.
PATCH / PUT <api>/recipes/1/
{
    "name": "Frost Burger",
    "description": "Meat and Lettuce on a chilled Frost Bun.\r\nIt's the only burger ever to be served cold.",
    "image_url": "https://oxygennotincluded.wiki.gg/images/Resource_Frost_Burger.png?5bef19&format=original",
    "dlc": "Base",
    "food_quality": {
        "Morale impact": "+5",
        "Quality": "Superb"
    },
    "spoil_time": 4,
    "kcal_per_kg": 6000,
    "source": "Gas Range",
    "source_image_url": "https://oxygennotincluded.wiki.gg/images/Gas_Range.png?caa6a2=&format=original",
    "calories_produced": 6000
}
```

### DELETE Method
```python
DELETE <api>/recipes/1/
# Deletes the recipe with the given ID.
```