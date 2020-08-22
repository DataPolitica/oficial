---
# Course title, summary, and position.
linktitle: Introducción
summary: Este es un libro de la csm.
weight: 1

# Page metadata.
title: Data Política 
date: "2018-09-09T00:00:00Z"
lastmod: "2018-09-09T00:00:00Z"
draft: false  # Is this a draft? true/false
toc: true  # Show table of contents? true/false
type: docs  # Do not modify.

# Add menu entry to sidebar.
# - name: Declare this menu item as a parent with ID `name`.
# - weight: Position of link in menu.
menu:
  example:
    name: Introducción
    weight: 1
---
# Manual de R para politólogos

## Introducción

Este `libro` fue creado como un soporte para el aprendizaje del software R (y R Studio) y está especialmente dirigido para aquellos estudiantes de ciencias sociales, en general, y ciencia política, en particular. 

Lo más resaltante de este manuel es que:

* **Presenta de una manera fácil y práctica los principales temas en estadística aplicada**
* **Incorpora herramientas audiovisuales al proceso de aprendizaje de estadística en ciencias sociales**
* **Utiliza memes**

The `courses` folder may be renamed. For example, we can rename it to `docs` for software/project documentation or `tutorials` for creating an online course.

## Sobre el autor



## Update site menu

After renaming or deleting the `courses` folder, you may wish to update any `[[main]]` menu links to it by editing your menu configuration at `config/_default/menus.toml`.

For example, if you delete this folder, you can remove the following from your menu configuration:

```toml
[[main]]
  name = "Courses"
  url = "courses/"
  weight = 50
```

Or, if you are creating a software documentation site, you can rename the `courses` folder to `docs` and update the associated *Courses* menu configuration to:

```toml
[[main]]
  name = "Docs"
  url = "docs/"
  weight = 50
```

## Update the docs menu

If you use the *docs* layout, note that the name of the menu in the front matter should be in the form `[menu.X]` where `X` is the folder name. Hence, if you rename the `courses/example/` folder, you should also rename the menu definitions in the front matter of files within `courses/example/` from `[menu.example]` to `[menu.<NewFolderName>]`.
