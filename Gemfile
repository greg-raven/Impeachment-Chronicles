source "https://rubygems.org"

gemspec

gem "jekyll", ENV["JEKYLL_VERSION"] if ENV["JEKYLL_VERSION"]
gem "kramdown-parser-gfm" if ENV["JEKYLL_VERSION"] == "~> 3.9"

gem "github-pages", group: :jekyll_plugins

group :jekyll_plugins do
  gem "jekyll-archives"
  gem "jekyll-feed", "~> 0.12"
  gem "jekyll-paginate"
  gem "jekyll-sitemap"
end
