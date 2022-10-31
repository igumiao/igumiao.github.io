---

permalink: /readme/
---
# Host a Resume On GitHub Page

A tutorial on how to host and format a resume using Markdown, 
a Markdown editor, GitHub Pages, and Jekyll.



## Demo

Here is the demo: [igumiao's resume](https://igumiao.github.io/zhou-resume)



## Prerequisites

- A resume formatted in [Markdown][markdownlink]
- Create your own [Github][githublink] account
- Install [Git][gitdownload] depending on your operating system
- Install [Jekyll][jekyllinstall]  
- A [markdown editor](https://www.shopify.com/partners/blog/10-of-the-best-markdown-editors)

### Quick Check
Before we get start, run each of the following command in console to check we have all the tools installed.
```
git --v
```
```
jekyll -v 
```
```
ruby -v 
```
```
gcc -v 
```
Each of the command should show up the version of the tool.

## Instructions

### 1. Create a repository
  - Head over to [GitHub][githublink] 

  - Create a new public repository named `username`.github.io, where `username` is your`username` on GitHub.
  
  - Click *add README.md* 

  - Click *create new repository*

### 2. Clone the repository
-  Go to the folder  where you want to store your project (on your computer)

```bash
cd pathOfFolder
```

- clone the new repository 
```bash
git clone https://github.com/username/username.github.io
```

### 3. Initialize your website
 
- Enter the project folder 
```bash
cd username.github.io
```
- Install the jekyll and bundler gems
```bash
gem install jekyll bundler
```
- Create a new Jekyll site at `./myresume`
```bash
jekyll new myresume
```

### 4. Run Locally with your resume.md

- Go to *./myresume* folder
```bash
cd myresume
```
- Move your *resume.md* into ./myresume

- Build the site and make it available on a local server
```bash
bundle add webrick
bundle exec jekyll serve
```
- Browse to http://localhost:4000/nameofyourResumeFile

### 5.  Add theme to our resume page
*In this tutorial, we will be using  [cayman theme][Caymanlink].*

We need to modify `_config.yml` and `Gemfile` these two files in our `/myresume` folder
- Add the following to your site's `_config.yml`
```
remote_theme: pages-themes/cayman@v0.2.0
plugins:
- jekyll-remote-theme 
```
- Find `group :jekyll_plugins do` in `Gemfile` and add 
```
gem 'jekyll-remote-theme'
```
- Add the following to your site's `Gemfile`,  
```
gem "github-pages", "~> GITHUB-PAGES-VERSION", group: :jekyll_plugins
```
*__NOTICE:__*
Replace `GITHUB-PAGES-VERSION` with the latest supported version you can find here: ["Dependency versions."](https://pages.github.com/versions/)
- comment out the line that starts with `gem "jekyll"` in `Gemfile`
``` 
#gem "jekyll", "~> 4.3.1"
```

### 6. Customize the page

- [Cayman theme][Caymanlink] will respect the following variables in _config.yml
```yml
title: [The title of your site]
description: [A short description of your site's purpose]
```
*You may change other variables of the page depending on the theme you choose*
### 7. Push it to github

- Change `url` in `_config.yml`
```
url: "https://username.github.io/" 
```

- Push it to GitHub
```bash
git add --all
git commit -m "Write Commit Message"
git push -u origin main
```



## More Resources

 - [Awesome Markdown Guide](https://www.markdownguide.org/basic-syntax/#links)
 - [Etter's book](https://github.com/matiassingers/awesome-readme)
 - [Github Page Docs](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll)
 - [Jekyll Docs](https://jekyllrb.com/docs/)
 - [Git Command Guide](https://www.freecodecamp.org/news/10-important-git-commands-that-every-developer-should-know/)
 

## License

[MIT](https://choosealicense.com/licenses/mit/)


## Screenshots

![App Screenshot](https://via.placeholder.com/468x300?text=App+Screenshot+Here)


## Authors

- [@igumiao](https://www.github.com/igumiao)


## FAQ

#### Question 1

Answer 1

#### Question 2

Answer 2



[markdownlink]:<https://www.markdownguide.org/basic-syntax/#links>
[githublink]: <https://github.com/>
[gitdownload]: <https://git-scm.com/downloads>
[jekyllinstall]: <https://jekyllrb.com/docs/installation/>
[Caymanlink]:<https://github.com/pages-themes/cayman>
