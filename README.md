# Hugo Villain Theme

Villain is a multi-page business theme with fullscreen hero images and fullwidth sections.

A modern villainous approach on the hero theme for Hugo.

[Live Demo](http://luciorq.github.io/hugo-villain-theme) |
[Installation](#installation)

![Hugo Villain Theme screenshot](https://github.com/luciorq/hugo-villain-theme/blob/main/images/screenshot-full.jpg)

# Features

### Content Types

- Services (Markdown)
- Work/Portfolio (Markdown)
- Features (Data)
- About (Markdown, Single Page, Shortcodes)
- Homepage (Markdown, Single Page, multiple .md files in one layout)

### Content Management

- This themes content is now all editable via markdown files.
- Includes examples where multiple .md files are sourced in a single layout to create fullwidth sections that have different locations in the HTML.
- The "Home" page uses multiple markdown files for the different homepage sections. It uses **headless bundles**.
- The "About Us" page uses multiple markdown files for its different sections. It uses **leaf bundles** and **shortcodes**.
- "Services" & "Work" use markdown files with layouts for list, single and summary views.

### Features

- Full-width responsive design
- Full-width/full-height hero image partial. Partial arguments include background-image, no background-image, background-image with overlay or just a solid color background.

### SCSS

- SCSS (Hugo Pipelines)
- Responsive design
- Bootstrap 4 grid and media queries
- The rest of the Bootstrap library is commented out by default but is ready to be @imported in the `style.scss`

### Speed

- 100/100 Google Lighthouse speed score
- Vanilla JS only
- Minified CSS under 20KB
- Minified JS under 20KB

### Menu

- Responsive mobile menu managed in `config.yaml`

### Content

- Robust example content included
- Royalty free images included

# Installation
### Install Hugo

To use this theme you will need to have Hugo installed. If you don't already have Hugo installed please follow the official [installation guide](https://gohugo.io/getting-started/installing/)

### Check Hugo version (Hugo 0.74.3+ Extended is required)

This theme uses [Hugo Pipes](https://gohugo.io/hugo-pipes/scss-sass/) to compile SCSS and minify assets. Please make sure you have the **Hugo Extended** version installed. If you are not using the extended version this theme will not not compile.

To check your version of Hugo, run:

```
hugo version
```

This will output the currently installed version of Hugo. Make sure you see `/extended` after the version number, for example `Hugo Static Site Generator v0.51/extended darwin/amd64 BuildDate: unknown` You do not need to use version v0.51 specifically, you can use any version of Hugo above 0.51. It just needs to have the `/extended` part

### Create a new Hugo site

```
hugo new site mynewsite
```

This will create a fresh Hugo site in the folder `mynewsite`.

### Install theme with Git

Clone this repo into the themes folder
```
cd mynewsite
git clone https://github.com/luciorq/hugo-villain-theme.git themes/villain
```

### Install theme from .zip file

You can download the .zip file located here https://github.com/luciorq/hugo-villain-theme/archive/main.zip.

Extract the downloaded .zip inside the `themes` folder. Rename the extracted folder from `hugo-villain-theme-main` -> `hugo-villain-theme`. You should end up with the following folder structure `mynewsite/themes/hugo-villain-theme`

### Copy example content

Copy the entire contents of the `mynewsite/themes/hugo-villain-theme/exampleSite/` folder to root folder of your Hugo site, i.e. `mynewsite/`

To copy the files using terminal, make sure you are still in the projects root, i.e. the `mynewsite` folder.

```
cp -a themes/hugo-villain-theme/exampleSite/. .
```

### Update config.{toml, yaml, json}

After you copy the `config.{toml, yaml, json}` into the root folder of your Hugo site you will need to update the `baseURL`, `themesDir` and `theme` values in `mynewsite/config.{toml, yaml, json}`

```
baseURL = "/"
themesDir = "themes"
theme = "hugo-villain-theme"
```

### Run Hugo

After installing the theme for the first time, generate the Hugo site.

You run this command from the root folder of your Hugo site ie `mynewsite/`

```
hugo
```

For local development run Hugo's built-in local server.

```
hugo server
```

Now enter [`localhost:1313`](http://localhost:1313) in the address bar of your browser.

# Configuration

### Homepage meta tags

Often a homepage requires special meta tags such as a meta description or Open Graph (og) meta data for twitter, facebook, etc. You can configure these values in the `config.{toml, yaml, json}`

```
// config.toml
...

  [params.homepage_meta_tags]
    meta_description = "a description of your website."
    meta_og_title = "My Theme"
    meta_og_type = "website"
    meta_og_url = "https://www.mywebsite.com"
    meta_og_image = "https://www.mywebsite.com/images/tn.png"
    meta_og_description = "a description of your website."
    meta_twitter_card = "summary"
    meta_twitter_site = "@mytwitterhandle"
    meta_twitter_creator = "@mytwitterhandle"

```

### Set meta tags on a per layout basis

You can set meta tags on a per template basis using a block. For example, you might want to write a custom meta description for the `/services` page. You can insert any valid HTML meta data inside the `{{ define "meta_tags }}` block at the top of a template.

```
// layouts/services/list.html
...

{{ define "meta_tags" }}
    <meta name="description" content="We offer a variety of services in the finance industry" />
{{ end }}

{{ define main }}
...
```

### Google Analytics

Add you Google Analytics ID to the `config.toml`

```
// config.toml
[params]
  google_analytics_id="UA-100000000-1"
```

### Menu

You can edit and add main menu links in the `config.toml` under `[[menu.main]]`

# Deploying to GitHub Pages

A descriptive tutorial can be found [here](https://gohugo.io/hosting-and-deployment/hosting-on-github/)
<!-- TODO write a paragraph about deplying to GH Pages-->

## License

This theme is heavily modified version of [hugo-hero-theme](https://github.com/zerostaticthemes/hugo-hero-theme) by @zerostaticthemes, without his work it wouldn't be possible to provide [hugo-villain-theme](https://github.com/luciorq/hugo-villain-theme) in it's current form.

If you fork or copy this theme the LICENSE file and the copyright notice on line 3 and 4 (where authors are listed) must not be changed. You cannot just replace the copyright line with your own name. Attribution in your README.md or on your site is also welcome but not required.
