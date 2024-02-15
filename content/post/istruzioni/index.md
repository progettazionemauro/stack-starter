---
title: Istruzioni
description: Benvenuto Mauro
date: 2024-02-11T19:44:06+01:00
image: cover.jpg
# math: 
# license: 
# hidden: false
# comments: true
tags: 
    - markdown
    - css
    - html
    - themes
categories:
    - themes
    - syntax
---

# **SOURCE OF LEARNING:**

Tutorial - [Lama Dev](https://www.youtube.com/watch?v=6BRZ-yHjYwo) 

# **HUGO RUNNING EXAMPLESITE**

Strumenti di Lavoro Typora a Zettlr
Here are the steps to create an example site using the Tikva theme in Ubuntu:

1. ## **Create a Directory for Your Hugo Site:** 

   Choose a location on your system where you want to create your Hugo site. Then, create a directory for your Hugo site:

   ```bash
   mkdir my-hugo-site
   ```

2. ### **Navigate to Your Hugo Site Directory:** 

   Change your current directory to the directory you just created:

   ```bash
   cd my-hugo-site
   ```

3. **Initialize a New Hugo Site:** Initialize a new Hugo site in your directory:

   ```bash
   hugo new site .
   ```

   This command creates the necessary directory structure and configuration files for your Hugo site.

4. **git inizialitation**

   ` git init `

5. **Clone the Tikva Theme Repository:** Clone the Tikva theme repository into the `themes` directory of your Hugo site:

   ```bash
   git clone --recurse-submodules https://github.com/geschke/hugo-tikva.git themes/tikva
   ```

   This command clones the Tikva theme repository and its submodules (if any) into the `themes/tikva` directory of your Hugo site.

6. **Copy the Example Site Content:** Copy the content of the `exampleSite` directory from the Tikva theme repository into the root of your Hugo site:

   ```bash
   cp -r themes/tikva/exampleSite/* .
   ```

   This command copies the content of the Tikva theme's example site into your Hugo site's root directory.

7. **Start the Hugo Server:** Run the Hugo server to build and serve the example site:

   ```bash
   hugo server --theme tikva
   ```

   The `--theme tikva` option tells Hugo to use the Tikva theme for your site.

8. **View the Example Site:** After starting the Hugo server, open your web browser and navigate to the URL provided by Hugo. By default, the URL should be `http://localhost:1313`.

That's it! You've now created a directory structure and set up an example site using the Tikva theme in Hugo. You can further customize and add content to your site following the theme's documentation and Hugo's documentation.

So now if you want to run from the root directory you can copy and past all the contents of exampleSite and after in hugo.toml

```bash
baseURL = 'https://example.org/'
languageCode = 'en-us'
title = 'My New Hugo Site'
theme="tikva"
```



**Create a new content and automatically generate the front matter from archetypes**

`hugo new content/posts/post08.md`
Content "/home/mauro/Scrivania/hugo/tikva_theme_example/content/posts/post08.md" created

Important note: directly copying another Markdown file from the content directory may not trigger the archetype functionality, as it bypasses the Hugo content creation mechanism.



# The meaning of _default folder and partial folder both inside layouts

In Hugo, the `_default` directory within the `layouts` directory holds templates that are used as defaults for rendering content types and sections when more specific templates are not available.

Here's a breakdown of the `_default` directory and its purpose:

1. **Content Types and Sections**: In Hugo, content can be organized into different types and sections. Content types define the structure and behavior of specific types of content, while sections represent different sections of your website (e.g., blog posts, pages, etc.).
2. **Default Templates**: The `_default` directory contains templates that serve as defaults for rendering content types and sections when no more specific templates are provided. For example, if you have a content type called "blog" and you don't provide a specific template for rendering individual blog posts, Hugo falls back to the `_default/single.html` template in the `_default` directory.
3. **Template Hierarchy**: Hugo follows a template hierarchy when rendering content. It first looks for specific templates based on the content's type and section. If it doesn't find a specific template, it falls back to the `_default` templates.
4. **Customization and Overrides**: You can customize the default behavior by providing more specific templates for content types and sections. For example, if you want to customize the layout for blog posts, you can create a `single.html` template in the `layouts/blog/` directory.
5. **`partials` Directory**: The `partials` directory contains reusable template snippets that are typically included within other templates. These snippets can be used to break down complex templates into smaller, more manageable pieces.

In summary, the `_default` directory contains default templates that Hugo uses when more specific templates are not provided. It plays a crucial role in the template hierarchy and allows for customization and flexibility in defining how different types of content are rendered on your Hugo website.

