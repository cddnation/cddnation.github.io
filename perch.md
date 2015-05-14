---
layout: page
title: Perch
group: "navigation"
---

CDD are big fans of the Perch CMS. Here's a collection of useful guides and patterns for how we develop perch sites inhouse.

> <p>Perch is the opium of the people</p>
> <p>- Karl Marx</p>

# Index

* Perch Style Guide
    - Folder structure
* Useful snippets
    - Title tag
    - Sitemap
    - Content Availability

---


## Perch Style Guide

### Folder structure

    templates/
    |-- categories/
    |   |-- category.html
    |-- content/
    |   |-- blocks-main.html
    |   |-- blocks-right_column.html
    |   |-- blocks/
    |       |-- full_width.html
    |       |-- two_column-text.html
    |       |-- two_column-image.html
    |       |-- three_column-text.html
    |   |-- collections/
    |       |-- authors.html
    |       |-- events.html
    |       |-- news.html
    |       |-- team_members.html
    |   |-- forms/
    |       |-- contact.html
    |-- layouts/
    |   |-- global/
    |       |-- header.php
    |       |-- footer.php
    |   |-- navigation/
    |       |-- breadcrumbs.html
    |       |-- item.html
    |       |-- sitemap.html
    |-- pages/
    |   |-- home.php
    |   |-- main.php
    |   |-- news.php
    |   |-- attributes/
    |       |-- default.html
    |       |-- seo.html
    |   |-- errors/
    |       |-- 404.php
    |-- pagination/
    |   |-- default.html
    |-- search/
    |   |-- form.html
    |   |-- result.html

---



## Useful snippets

### Content Availability
Use the following snippet, to see what content you have available in your Perch template.
    
    <perch:showall />



### Title Tag

These snippets will allow the CMS user to set the title for a page. If that value has not been set, it will display the default as set by the CMS itself. Here we amend the seo.html template, but you can create your own template and include this in default.html if you prefer.

In your `templates/layouts/global/header.php` file, add the following within the `<head>` tag:

    <?php PerchSystem::set_var('default_page_title', perch_pages_title(true)); ?>

    <?php
        perch_page_attributes(array(
            'template' => 'seo.html'
        ));
    ?>


In your seo.html add the following:


    <title>
        <perch:if exists="pagetitle"><perch:pages id="pagetitle" label="Title Tag" type="text" /><perch:else><perch:content id="default_page_title" /> | Project name</perch:if>
    </title>



### Sitemap

Follow the instructions on [this page](http://solutions.grabaperch.com/html-and-css/how-do-i-create-a-google-sitemap) to get sitemaps working.
