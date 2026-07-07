# Running Jekyll Docs Locally on macOS

Steps to get a GitHub Pages / Jekyll-based docs site running locally, assuming Jekyll is already installed.

## 1. Make sure you have a `Gemfile` (create a Gemfile using touch or vim and add the below content)

GitHub Pages repos almost always ship with a `Gemfile` (and `Gemfile.lock`) that pins the `github-pages` gem version. If yours doesn't have one, create it:

```ruby
source "https://rubygems.org"
gem "github-pages", group: :jekyll_plugins
```

## 2. Install Bundler and dependencies

```bash
gem install bundler
bundle install
```

If `bundle install` fails with permission errors, you're likely hitting macOS's protected system Ruby. Fix by installing your own Ruby via `rbenv` or `asdf` rather than fighting `sudo`:

```bash
brew install rbenv
rbenv install 3.2.2   # or whatever version matches the Gemfile.lock BUNDLED WITH
rbenv local 3.2.2
gem install bundler
bundle install
```

## 3. Serve the site

From the repo root:

```bash
bundle exec jekyll serve
```

Then open `http://localhost:4000` in your browser. Use `bundle exec` (not just `jekyll serve`) so it uses the gem versions locked in your `Gemfile.lock`, matching what GitHub Pages actually runs.

## Common Mac-specific snags

- **Xcode command line tools missing** — some gems need to compile native extensions:
  ```bash
  xcode-select --install
  ```
- **`nokogiri` or `ffi` build errors on Apple Silicon** — usually fixed by:
  ```bash
  brew install libxml2 libxslt
  ```
  then retry `bundle install`.
- **Live reload while editing** — add `--livereload`:
  ```bash
  bundle exec jekyll serve --livereload
  ```
- **Port already in use**:
  ```bash
  bundle exec jekyll serve --port 4001
  ```

## Note

If "github docs" refers specifically to the `github/docs` repo (the one powering docs.github.com), that repo actually runs on Node.js/Next.js now, not Jekyll. The steps above apply to a more classic GitHub Pages-based docs site.
