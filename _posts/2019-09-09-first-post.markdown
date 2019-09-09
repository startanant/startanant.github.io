---
layout: post
title:  "Setting up your GitHub Pages site with Jekyll"
date:   2019-09-09 14:33:46 -0400
tags: jekyll update github git
---

1. On GitHub, create a new repository called `<username>.github.io` (Follow steps 1-5 [here](https://help.github.com/en/articles/create-a-repo). It is not necessary to initialize this repository with a README now. Click **Create repository**.)

2. On your local machine, install [Ruby](https://www.ruby-lang.org/en/downloads/).

3. Install bundler

	`$ gem install bundler`

4. Create a new repo locally with the same name.

	`$ git init <username>.github.io`

5. Change directory
	`$ cd <username>.github.io`

6. Create a gemfile and add the GitHub Pages gem.
	
	`source 'https://rubygems.org'`
	
	`gem 'github-pages', group: :jekyll_plugins`

7. Install Jekyll and other dependencies from the GitHub Pages gem.

	`$ bundle install`

8. Create a new Jekyll project in the current folder we’re in. The --force option is to tell Jekyll to force this command.

	`$ jekyll new . --force`

9. Edit the Gemfile, delete the # at the beginning of this line:

	`#gem "github-pages", group: :jekyll_plugins`

10. Add a new remote 
	
	`$ git remote add origin https://github.com/	username/username.github.io.git`

11. It's a good time to setup/review your github global config settings
	
	`$ git config --global user.name "username"`
	
	`$ git config --global user.email "user@email.com"`

12. Add or stage your changes.

	`git add .`

13. Commit your changes with a comment.
	
	`git commit -m "First commit"`

14. Push your changes to your remote repository on GitHub.
	
	`git push -u origin master`

15. Your GitHub Pages site is now ready at
	
	`username.github.io`
![Jekyll welcome page](/assets/jekyll_welcome.png)

16. Nothing else to see here. No more excuses. Read the [docs](https://jekyllrb.com/docs/posts/) and start blogging.
