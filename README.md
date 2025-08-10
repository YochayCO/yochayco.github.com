## How to run locally

1. **Install the Theme**

   Run the following command to install the theme and its dependencies:

   ```bash
    bundle
   ```

2. **Run Your Site**

   Start your Jekyll site with:

   ```bash
    bundle exec jekyll serve
   ```

## Usage

This theme provides several **layouts** for different types of pages. Each layout has specific front matter variables to customize the content and appearance.

- **Home Layout**: Main landing page layout. Displays a profile image, main content area, and reference to blog and project section.

- **Projects Layout**: Used to **list a collection of projects**. Requires collection configuration in your `_config.yml`.

- **Blog Layout**: Builds a **blog page with posts**. Displays posts sorted by date with optional category filtering.

- **Post Layout**: Used for **individual blog posts**. Supports various metadata like categories, excerpts, and author information.

- **Project Layout**: Designed for **individual project pages**. Includes project image, description, and tags.

**I will be describing each layout on a near future, if you have a question just ask.**

## Configuration

### Navbar and Footer

The navbar filters pages to be displayed based on a front matter called `nav`. These pages will appear in the navbar listed by the front matter `title`. If there is no `title`, then the filename is used. So, if you want to add a page to the navbar, **don't forget to add `nav: true`**.

Similarly, the same applies to footer pages. For example, if you add a `privacy-policy.markdown` page, you may want to add it to the footer but not to the navbar. The front matter will look like this:

```yaml
---
nav: false
footer: true
....
---
```

**Posts and Projects not count like pages.**

### Contact Channels

Contact channels are displayed in the home layout and the footer. To configure this, please add each one to your `_config.yml` file like this:

```yaml
contact_channels:
  email: "andres.ch@protonmail.com"
  github: "https://github.com/a-chacon"
  telegram: "https://t.me/a_chacon"
  stackoverflow: "https://stackoverflow.com/users/16847024/andr%c3%a9s"
  discord: "https://discord.com/users/673943171369140252"
  mastodon: "https://lile.cl/@achacon"
```

**If you need to add a new one, just ask or send a PR**

### Favicon and other head element customizations

If you want to have a custom [favicon](https://en.wikipedia.org/wiki/Favicon) for your site, or in any other way add more to the `<head>` element for all pages, then you can simply create a new file `custom_head.html` in the `_includes` directory and put in any such customization. For example, if you want to add a favicon that is location at (say) `assets/images/logo.avif`, then you simply need to create a new file `_include/custom_head.html` and put the following in it.

```html
<link rel="shortcut icon" type="image/avif" href="/assets/images/logo.avif" />
```

_Note: This theme already contains a file `assets/images/logo.avif`, and so if you create a new one in your site, then it will overwrite the theme file._

## Plugins

The Awesome Jekyll theme comes with the [`jekyll-seo-tag`](https://github.com/jekyll/jekyll-seo-tag) plugin preinstalled to ensure your website gets the most useful meta tags. See [usage](https://github.com/jekyll/jekyll-seo-tag#usage) to learn how to set it up.

It also includes [`jekyll-archives`](https://github.com/jekyll/jekyll-archives) to generate category web pages.

This theme is built with **multi-language support** by default, based on the excellent gem [`jekyll-polyglot`](https://github.com/untra/polyglot). It is also included as a plugin. The default site language is English, but if you want to **use this in Spanish, simply set this in your config file**: `default_lang: es`. And if you want to set a different language other than English or Spanish, please create a file in `_data/[your lang]/strings.yml`, using an existing file as template.

## Contributing

Bug reports and pull requests are welcome on GitHub at <https://github.com/a-chacon/awesome-jekyll-theme>. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](https://www.contributor-covenant.org/) code of conduct.

## Development

To set up your environment to develop this theme, run `bundle install`.

Your theme is setup just like a normal Jekyll site! To test your theme, run `bundle exec jekyll serve` and open your browser at `http://localhost:4000`. This starts a Jekyll server using your theme. Add pages, documents, data, etc. like normal to test your theme's contents. As you make modifications to your theme and to your content, your site will regenerate and you should see the changes in the browser after a refresh, just like normal.

When your theme is released, only the files in `_layouts`, `_includes`, `_sass` and `assets` tracked with Git will be bundled.
To add a custom directory to your theme-gem, please edit the regexp in `awesome-jekyll-theme.gemspec` accordingly.

## License

The theme is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).
