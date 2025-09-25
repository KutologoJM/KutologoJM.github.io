---
title: Oni Recipes API
author: KutologoJM
description: An api used to add and manage recipes from Oxygen Not Included within your browser.
date: 2025-09-20
categories: [api-endpoint]
tags: [api]
permalink: /oni-recipes-api/
---

## ONI FOOD RECIPES API

### [Try the api here](oni-recipe-api-test.md)
#### OR
#### [Check out the source code on GitHub](https://github.com/KutologoJM/oni-recipe-api/)

> This API was designed to allow users to easily store, access and manipulate ONI Food Recipes.

[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)
![Python](https://img.shields.io/badge/Python-3.12+-blue.svg)
![Django](https://img.shields.io/badge/Django-5.2-green.svg)
![DRF](https://img.shields.io/badge/DRF-3.x-red.svg)
![Poetry](https://img.shields.io/badge/Poetry-managed-informational.svg)

---

## API Structure
> Optionally visit: [API SWAGGER DOCS](https://oni-recipe-api-v3.onrender.com/api/docs/swagger/) for OpenAPI Documentation.

___

> The API consists of three major parts. The [Recipes][Recipes], [Ingredients][Ingredients] and [Recipe Ingredients][Recipe Ingredients] containers.
>
> **Recipes**: The main container that stores the main information about the recipes.
>
> **Ingredients**: Holds information about all items that can serve as ingredients for recipes.
>
> **Recipe Ingredients**: This container allows recipes to be linked to specific ingredients and their particular measurements for that recipe.

[Recipes]: {{ '/oni-recipes-api/recipes/' | relative_url }}
[Ingredients]: {{ '/oni-recipes-api/ingredients/' | relative_url }}
[Recipe Ingredients]: {{ '/oni-recipes-api/recipe-ingredients/' | relative_url }}
