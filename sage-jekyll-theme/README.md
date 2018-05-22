# sage-jekyll-theme

This is the ruby gem theme used by Sage Group plc.

## Installation

Add this line to your Jekyll site's `Gemfile`:

```ruby
gem "sage-jekyll-theme"
```

And add this line to your Jekyll site's `_config.yml`:

```yaml
theme: sage-jekyll-theme
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install sage-jekyll-theme

## Usage

### Layouts

- `default` - use for basic mapping pages
- `home` - use for index/home html pages where you need a blank slate
- `api-reference` - use for API reference, this includes the split screen view of code
- `documentation` - use for documentation/guides, this includes the side bar
- `post` - use for blog postings

### Language file

You should add the following skeleton as the UI text file `_data/ui-text.yml`. You can localize it later to other languages.

```yml
navbar:
  toggle_tip: "Toggle navigation"
  search_url: "https://www.google.com/search"
  search_input_placeholder: "Search with Google"
  search_button_label: "Search"

footer:
  copyright:
    text: "Copyright &copy;"
    entity: "Sage Group plc"
    url: "https://www.sage.com"
  content_license:
    prefix: "Page content licensed under"
    name: "Creative Commons Attribution 4.0"
    url: "http://creativecommons.org/licenses/by/4.0/"
  code_license:
    prefix: "Code samples licensed under"
    name: "Apache v2.0"
    url: "http://www.apache.org/licenses/LICENSE-2.0"
```


## Development

To set up your environment to develop this theme, run `bundle install`.

Your theme is setup just like a normal Jekyll site! To test your theme, run `bundle exec jekyll serve` and open your browser at `http://localhost:4000`. This starts a Jekyll server using your theme. Add pages, documents, data, etc. like normal to test your theme's contents. As you make modifications to your theme and to your content, your site will regenerate and you should see the changes in the browser after a refresh, just like normal.

When your theme is released, only the files in `_layouts`, `_includes`, `_sass` and `assets` tracked with Git will be bundled.
To add a custom directory to your theme-gem, please edit the regexp in `sage-jekyll-theme.gemspec` accordingly.
