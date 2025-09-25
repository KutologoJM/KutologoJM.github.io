---
title: Oni Recipes API - Recipe Ingredients
author: KutologoJM
description: Recipe Ingredients Description
categories: [api-endpoint]
tags: [api]
permalink: /oni-recipes-api/recipe-ingredients/
---

# Recipe Ingredients Model
## Fields:

- recipe
    - Read-only
    - The name of the recipe this ingredient is associated with.
- recipe_id
    - This field is required.
    - The primary key of the recipe that will be used for this relationship.
- ingredient
    - Read-only
    - Displays information about the associated ingredient.
- ingredient_id
    - This field is required.
    - The primary key of the ingredient that will be used for this relationship.
- amount_required
    - This field is required.
    - The numerical amount of the given ingredient that is required for the recipe.
- unit
    - This field is required.
    - The unit that the ingredient will be represented in for this recipe.
- role
    - This field is required.
    - choices Main OR Alternate
        - Main: This is a primary ingredient and is required.
        - Alternate: This is an alternate ingredient, can be swapped with a main ingredient and is not required.


### GET Method
```python
GET <api>/recipe-ingredients/1/
# This will allow you to view a specific recipe's ingredients based on its ID.

GET <api>/recipe-ingredients/
# This will display all recipe-ingredient relationships currently saved within the model.

GET <api>/recipe-ingredients/?ordering=<field_name>
# This will allow you to sort all the recipe-ingredient relationships by your desired field.
example field names:
    - recipe
    - ingredient
    - role
ascending: field_name
descending: -field_name
```

```python
GET <api>/recipe-ingredients/1/
{
  "recipe": "Frost Burger",
  "ingredient": {
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
  },
  "amount_required": 1200,
  "unit": "kcal",
  "role": "main"
}
```

### POST Method
```python
#  Allows you to create a new recipe and ingredient relationship.
POST {
  "recipe_id": null,
  "ingredient_id": null,
  "amount_required": null,
  "unit": "",
  "role": null
}
```

```python
# An example of a recipe "Frost Burger" and Ingredient "Frost Bun" relationship being created.
POST {
  "recipe": "Frost Burger",
  "ingredient": {
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
  },
  "amount_required": 1200,
  "unit": "kcal",
  "role": "main"
}
```

### PATCH / PUT Method
```python
# Allows you to modify a part or all of a given recipe ingredient relationship.
PATCH / PUT <api>/recipe-ingredients/1/
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
# An example patch changing the associated recipe from "Frost Burger" to "Surf'n'Turf"
PATCH / PUT <api>/recipe-ingredients/1/
{
  "recipe": "Surf'n'Turf",
  "ingredient": {
    "name": "Barbeque",
    "description": "The cooked meat of a defeated critter.\r\nIt has a delightful smoky aftertaste.",
    "slug": "barbeque",
    "dlc": "Base",
    "ingredient_image_url": "https://oxygennotincluded.wiki.gg/images/Resource_Barbeque.png?512e4c=&format=original",
    "spoil_time": 4,
    "food_quality": {
      "Quality": "Good",
      "Morale impact": "+3"
    },
    "kcal_per_kg": 4000,
    "source": "Electric Grill",
    "source_image_url": "https://oxygennotincluded.wiki.gg/images/9/97/Electric_Grill.png?7e3bb5=&format=original"
  },
  "amount_required": 4000,
  "unit": "kcal",
  "role": "main"
}
```

### DELETE Method
```python
DELETE <api>/recipe-ingredients/1/
# Deletes the recipe ingredient relationship with the given ID.
```