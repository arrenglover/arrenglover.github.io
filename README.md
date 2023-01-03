
### Installation

`sudo apt-get install ruby-full build-essential zlib1g-dev`

gems are packages for the ruby language. don't do a system install for gems to avoid conflicts in the future.

```
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/.gems"' >> ~/.bashrc
echo 'export PATH="$HOME/.gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

`bundler` installs gems based on config files.
`jekyll` separates website formatting and content.

`gem install jekyll bundler`

### Make the website

clone the github.io repository and `cd` to the root folder. Create the base files jekyll uses

`jekyll new --skip-bundle`

modify the versions of jekyll and gihub-pages packages used
`vim Gemfile`

```
gem "jekyll", "~> 3.9.2"
gem "github-pages", "~> 227", group: :jekyll_plugins
```

modify the _config file

```
#theme: minima
remote_theme: pages-themes/minimal@v0.2.0
plugins:
- jekyll-remote-theme
```

`bundle install`

see https://pages-themes.github.io/minimal/ for examples on how to add content

### Host the website locally with Jekyll

`bundle exec jekyll serve`

go to:
`http://localhost:4000`
with a web browser


### Host the website on-line

set the branch in repository settings on github.com
push the repo to a branch that github is serving to https://arrenglover.github.io
