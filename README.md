# Semver.org

This is the site at https://semver.org/ that describes the Semantic Versioning specification.

## Adding a translation

1. Create a new folder in `lang/` with the appropriate language tag
2. Add a translated `index.md` to that folder
3. Add a translated `spec/vX.X.X.md` for the latest spec to that folder
4. Ensure all files have the appropriate `title` and `language` front matter (see others as an example)
5. Add the language to the `_config.yml` file

## Running locally

1. Install [Ruby](https://www.ruby-lang.org/en/downloads/) and [Bundler](http://bundler.io/).
2. Install Jekyll and other dependencies from the gem:
   ```
   bundle install
   ```
3. Run the site locally:
   ```
   bundle exec jekyll serve
   ```
4. Open http://localhost:4000.

## Running locally with docker-compose

If you have [docker-compose](https://docs.docker.com/compose/) installed:

1. Build Docker image and start container instance:
   ```
   docker-compose up
   ```
2. Open http://localhost:4000.

## Deploying to Pivotal Web Services

1. Install the CF CLI
2. Authenticate with run.pivotal.io
   ```
   cf login -a "https://api.run.pivotal.io" -o "Data R&D" -s "gp-releng"
   ```
3. CF Push the application
   ```
   cf push SemiSemver -c "bundle exec jekyll serve --port 8080 --host 0.0.0.0" -b ruby_buildpack
   ```
4. Open https://semisemver.cfapps.io/
