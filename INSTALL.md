# Troubleshooting local Jekyll installation

## macOS

If `sudo gem install bundler` fails with:

  ERROR:  While executing gem ... (TypeError)
      no implicit conversion of nil into String

… then `sudo gem update --system`

If `bundle install'` fails with:

  An error occurred while installing nokogiri (1.6.8.1), and Bundler cannot continue.
  Make sure that `gem install nokogiri -v '1.6.8.1'` succeeds before bundling.

… then `bundle config build.nokogiri --use-system-libraries` and retry.


## Ubuntu

1. Run `bundle update` to check that the ruby bundler is installed
    1. If it is not installed do ```sudo apt install ruby-bundler```
2. Run `bundle install`
  * Problem running `bundle install`: `Gem::Ext::BuildError: ERROR: Failed to build gem native extension.`
     * Run `sudo gem install json -v '1.8.6' -- --use-system-libraries`
   * Problem with `sudo gem install json...`: `ERROR:  Error installing json:`
     * Run `sudo apt-get install ruby-dev`
3. Run `bundle exec jekyll build`
4. Run `bundle exec jekyll serve` to start up a local instance.
5. Now you can browse the content in your favorite web browser
