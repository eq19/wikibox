# jekyll-wikibox

This project is supposed to serve as foundation of a responsive and flexible guerilla wiki for hackers.
It transfers your markdown/textile notes to satic html layout inspired by sublime text editor.

- Manual
  - Live Demo
  - Installation
  - Local Deployment
  - Web Deployment
  - Customization
  - Project Structure
- Project Planning
  - Features (DONE)
  - Initial Backlog (TBD)
- References
  - Core Technologies
  - Related Technologies
  - Feature Inspirations
  - Design Inspirations
  - Markup Languages

## Manual

### Live Demo

- Available via `branch gh-pages` (github pages)  
  `http://dataduke.github.com/jekyll-wikibox` (to be done)

### Installation

1. install ruby
2. install jekyll `sudo gem install jekyll`
3. fork/clone/check out this github project

### Local Deployment

1. change to `cd ~/github/jekyll-wiki`
2. run `jekyll --server` 
3. open `http://localhost:4000/`

### Web Deployment

- GitHub Hosting: Please refer to github pages help.
- Other web hoster: Please refer to jekyll wiki/help.

### Customization

    ./_config.yml           # configuration
    ./_themes/themename     # themes; move all files/folders contained in a theme to root folder (and override)

### Themes

Sublime Text Theme

![Version alpha.03 - Sublime Text](https://github.com/dataduke/jekyll-wikibox/raw/master/.info/snapshot-version-a03-sublimetext.jpg)

Paint Bucket Theme

![Version alpha.03 - Paint Bucket](https://github.com/dataduke/jekyll-wikibox/raw/master/.info/snapshot-version-a03-paintbucket.jpg)

### Structure

    .
    |-- .info               # can be ignored; used for project information only
    |-- .temp               # can be ignored; used at development for backup of important files
    |-- _includes           # used for building index pages
    |   |-- main-index-sidebar.md
    |   |-- main-index-box-N.md
    |   |-- box-N-index-sidebar.md
    |   |-- box-N-index.md
    |-- _layouts
    |   |-- default.html
    |   |-- post.html
    |-- _themes             
    |-- _site               # not checked in; created by jekyll as deployment directory
    |-- _plugins 
    |   |-- additional-feature-X
    |-- assets              # for layout dependencies only
    |   |-- css
    |       |-- style.css
    |   |-- img
    |   |-- js
    |   |-- favicon.ico
    |-- box000               # box001-005 for testing; more boxes can be added/renamed/deleted
    |   |-- _posts
    |   |   |-- 2013-01-01-hello-world.markdown    # .md or .textile or .taskpaper
    |   |   |-- 2013-01-01-hello-world             # folder for post attachments
    |   |       |-- attachment-1.jpg
    |   |       |-- attachment-2.pdf
    |   |-- atom.xml
    |   |-- index.html
    |-- _config.yml
    |-- index.html
    |-- atom.xml

## Project Planning

Please refer to the following files:

    ./CHANGELOG.md              # contains version history
    ./JEKYLL-WIKIBOX.taskpaper  # contains planned features and current backlog
    ./README.md                 # contains general information

### Features (DONE)

- multiple boxes/repositories (blogs) for notes (markdown, textile)
- sort by date created

### Initial Backlog (TBD)

- basic layout  
  - fix horizontal scrolling
  - post layout
  - box layout
- advanced layout
  - card stack view
  - show/hide box column by selesction in main view
  - allow drag and drop to sort columns
- sorting
  - sort by date modified
  - sort by category
  - sort by tags
  - sort by name
- set box/post/content column width
  - 300px
  - 600px
  - 900px
- switch scrolling for post
  - horizontal
  - vertical 
- markup
  - add syntax highlighting
  - add mathjs
- special cards
  - add support for .taskpaper files
  - add support for .rst file (reStructuredText)
  - add support for learning card attribute (POI pile of index cards)
- attachment and image support
  - attachment folder has same name as post (sits in same directory)
  - create automatic links to images in attachment folders
  - add support for post/card attachments (contained in post-name-folders)
- add top bar
  - add search box on left
  - add breadcrumb path
  - filter box (for highlighting words in content area)
- add config file
  - global font with font size
  - contains attributes for each box (box name, relative box path, box foreground color, box background color)
- themes
  - finish sublime text theme
  - build theme Simple Github / jekyll-bootstrap with [twitter theme](http://themes.jekyllbootstrap.com/)
  - build theme [Apple Developer Wiki](https://developer.apple.com/technologies/ios/)
  - build theme [FoldingText Website](http://www.foldingtext.com/)
  - build theme [docs](https://readthedocs.org/)
  - build theme paint-pot-like (website suitable)
  - build theme scientific thesis (website suitable)
  - add theme switcher
- individual columns
  - show/hide boxes on landing page
  - change view/sorting of each box individually
- small appify
  - launch local website in safari or fluid.app via alfred app
  - search local website in safari or fluid.app via alfred app
  - only create local relative links that don't need a webserver (static html only), like:
    `<a href='./folder/2011-12-29-jekyll-introduction.html' title='Jekyll Introduction'>Jekyll Introduction</a>`
  - use [fluid.app](http://fluidapp.com) and [fake.app](http://fakeapp.com/)
- big appify/headless running
  - create gem for jekyllwiki
  - wiki tructure: `~/wikiroot/box/category/note.md` 
  - wiki usage: `cd ~/wikiroot` and `jekyllwiki --server 4444` and webbrowser `http://localhost:4444`
  - alternative appify wiki with fluid.app 
  - create browser app which wraps all dependencies (jekyll, ruby)
  - implement toggle to source view on post layout
  - allow editing inside source view
  - separate/strip boxes to folders outside of app
  - allow only custom folder path for boxes outside of wiki instance
- mobile appify
  - make it deployable via dropbox for mobile use (ios, android)
  - every box has its own feed which is usable by rss-reader apps

## References

### Acknowledgments

### Core Technologies

- [ruby](http://www.ruby-lang.org/en/)
- [jekyll](https://github.com/mojombo/jekyll)

### Markup Languages

- [markdown](http://daringfireball.net/projects/markdown/) by John Gruber
- [multimarkdown](http://fletcherpenney.net/multimarkdown/) by Fletcher Penny
- [github flavored markdown](https://help.github.com/articles/github-flavored-markdown) by GitHub
- [textile](http://textism.com/tools/textile/) by Dean Allan
- [taskpaper](http://www.hogbaysoftware.com/products/taskpaper) by Jesse Grosjea

### Higher-Level Languages

- [YAML](http://www.yaml.org): data serialization;
- [{{ mustache }}](http://mustache.github.com), [js github repho](https://github.com/janl/mustache.js): tag expansion;
- [Sass](http://sass-lang.com): CSS3 abstraction; .scss or .sass;
- [Haml](http://haml.info), [doc](http://haml.info/docs/yardoc/file.REFERENCE.html): HTML abstraction; .html.haml;
- [less](http://lesscss.org/), [github repo](https://github.com/cloudhead/less.js): CSS3 extension for dynamic behaviour (variables etc.);
- [liquid](http://www.liquidmarkup.org/), [help](https://github.com/mojombo/jekyll/wiki/liquid-extensions), [github repo](https://github.com/Shopify/liquid), [wiki](https://github.com/Shopify/liquid/wiki/Liquid-for-Designers): template system;
- [ERuby](http://de.wikipedia.org/wiki/ERuby), [erb](http://ruby-doc.org/stdlib-1.9.3/libdoc/erb/rdoc/ERB.html): Ruby templating; .erb, .html.erb, .xml.erb;
- [CoffeeScript](http://coffeescript.org/)

### Related Technologies

- [jekyll-asset-pipeline](https://github.com/matthodan/jekyll-asset-pipeline), [blog](http://matthodan.com/2012/11/22/jekyll-asset-pipeline.html)
- [jekkll-asset_bundler](https://github.com/moshen/jekyll-asset_bundler)
- [jekyll-bootstrap](https://github.com/plusjade/jekyll-bootstrap) 
- [multi-blog-jekyll](https://github.com/ggarron/multi-blog-jekyll)
- [github pages](http://pages.github.com/), [help](https://help.github.com/categories/20/articles) 
- [octopress](https://github.com/imathis/octopress)
- [ruhoh](http://ruhoh.com)

### Feature Inspirations

 - **PoIC** (Pile of Index Cards)
    - [Wiki](http://pileofindexcards.org/)
    - [Blog](http://pileofindexcards.org/blog/)

### Design Inspirations

- Theme **sublimetext** (default)
  - [Sublime Text](http://www.sublimetext.com/)
  - [Soda-Dark.sublime-theme](https://github.com/buymeasoda/soda-theme)
  - [Monokai-Soda.tmtheme](https://github.com/simeonv/st2-color-schemes)

## Design Frameworks

- jQuery
- Bootstrap
