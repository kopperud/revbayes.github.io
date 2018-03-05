revbayes-tutorials
==========================

This is the repository for the RevBayes tutorials website.

To do list!
- add Hackathons page (kinda like the workshops page)
- populate all the workshops to the new site

Setting up this repo locally
=================

Because this site makes use of third party jekyll plugins, the static site is stored on branch `master`, while the source files are stored on branch `source`.

After first cloning this repository you should checkout the `source` branch. Then you should clone the `master` branch again to the `_site` directory.

	git checkout source
	git clone git@github.com:willpett/revbayes_tutorials.git _site

In order to build the site you will need `jekyll`, see instructions below to install.

Making changes to the site
=================

When making changes to the site, you should always work on the `source` branch. After committing your changes to `source`, simply run the `update-site.sh` script. This script will take care of the steps involved to push both the `source` and `master` branches to github. 

	sh update-site.sh

Setting up jekyll
=================

In order to build the site you will need to install [`jekyll`](https://jekyllrb.com/docs/installation/).

To install `jekyll` and `bundler` (or update them):

    gem install jekyll bundler

If you get a permission error, you can install the `jekyll` and `bundler` gems
in your home folder using:

    export GEM_HOME=~/.gem
    gem install jekyll bundler
    
NOTE: You may get errors here that you need to update ruby to install these
gems. 

Next, move into the `revbayes_tutorials` repo, and install required gems via:

    bundle install

Now, you should be able to build and serve the static HTML with:

    bundle exec jekyll serve

If you get the error "invalid byte sequence in US-ASCII", this seems to fix it:

    export LC_CTYPE="en_US.UTF-8"
    export LANG="en_US.UTF-8"
