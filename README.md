---

permalink: /readme/
---
# Host a Resume On GitHub Page

A tutorial on how to host and format a resume using Markdown, 
a Markdown editor, GitHub Pages, and Jekyll.


----------------------
## Demo

Here is the demo: [igumiao's resume](https://igumiao.github.io/zhou-resume)


----------------------
## Prerequisites

- A resume formatted in [Markdown][markdownlink]
- Create your own [GitHub][githublink] account
- Install [Git][gitdownload] depending on your operating system
- Install [Jekyll][jekyllinstall]  
- Install [markdown editor](https://www.shopify.com/partners/blog/10-of-the-best-markdown-editors)

### Quick Check
Before we get started, run each of the following commands in the console to check we have all the tools installed.
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
Each of the commands should show up the version of the tool.

----------------------
## Instructions
>As mentioned in Etter's book, it is essential to define the audience when doing modern technical writing like this README.
>
>Since you are students who don't have much experience with Git, Jekyll, Markdown, and GitHub, it's necessary to give you clear and straightforward instructions. The instruction should only involve critical parts. 
>The instructions use the same word to describe the name of a file, the variable name, or the page link to keep the style to avoid confusion.

#### 1. Create a repository

>We will be using Git as a Distributed Version Control tool. Etter points out in the book, says that distributed version control system like GitHub has better performance. 
>
>You also need to add a README.md file in the root of the repository to include a quick summary of your project to follow the principle of modern technical writing.

- Head over to [GitHub][githublink] 

- Create a new public repository named `username`.github.io, where the `username` is your `username` on GitHub.
  
- Click *add README.md* 

- Click *Create a new repository*

#### 2. Clone the repository
>Since you might not have experience with Git. Thus, it's essential to demonstrate how to clone the repository.
>
>Here we demonstrate how to clone the repository and save the file on the local machine so we can work offline. Working offline is a great advantage compared to a centralized system where people must edit one file online.

-  Go to the folder  where you want to store your project (on your computer)
```bash
cd pathOfFolder
```
- Clone the new repository 
```bash
git clone https://github.com/username/username.github.io
```

#### 3. Initialize your website

>Static websites are excellent platforms to show your documentation or blogs. According to Etter???s book, static websites don???t require a database or complex installation procedures. Jekyll is a static website generator tool that helps you create a static website and modify the content easily. 
>
>Here we are using Jekyll to generate a static website.

- Enter the project folder 
```bash
cd username.github.io
```
- Install the Jekyll and bundler gems
```bash
gem install jekyll bundler
```
- Create a new Jekyll site at `./myresume`
```bash
jekyll new myresume
```

#### 4. Run locally with your resume.md

>Markdown is a lightweight markup language for creating formatted text. Its well-designed syntax appeals to developers. It???s easy to convert to web base language. It???s easier to modify compared to HTML. Etter suggests in the book to use Markdown for software documentation.
>
>Here we use a resume formatted in Markdown with Jekyll to generate our resume page.

- Go to `./myresume` folder
```bash
cd myresume
```
- Move your `resume.md` into `./myresume`
  
- Build the site and make it available on a local server
```bash
bundle add webrick
bundle exec jekyll serve
```
- Browse to http://localhost:4000/nameofyourResumeFile

#### 5.  Add a theme to our resume page

>A well-formatted web page is good, but we can make it looks more appealing by adding a theme. GitHub Pages have several themes that will your page more attractive. In this way, we also are encouraging others to write well-designed documentation.
>
>Here we are using GitHub Page's theme to modify our static webpage

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
- Add the following to your site's `Gemfile`
```
gem "github-pages", "~> GITHUB-PAGES-VERSION", group: :jekyll_plugins
```
*__NOTICE:__*
*Replace `GITHUB-PAGES-VERSION` with the latest supported version you can find here: ["Dependency versions. Comment](https://pages.github.com/versions/)*

- Comment out the line that starts with `gem "jekyll"` in `Gemfile`
``` 
#gem "jekyll", "~> 4.3.1"
```
- Add the following to your site's `_config.yml`
```
markdown: kramdown
```

#### 6. Customize the page

>Here we are using variables to customize our static webpage

- [Cayman theme][Caymanlink] will respect the following variables in `_config.yml`
```yml
title: [The title of your site]
description: [A short description of your site's purpose]
```

#### 7. Push it to GitHub

>Now, we are pushing our projects to GitHub. Pushing is like uploading our files such that our documentation and codes will stay in sync all the time. 
>
>The audience is the student with no experience with Git, thus it's important to demonstrate how to push.

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

#### 8. View your resume on GitHub Page

- Optionally you can permalink on the top of your `resume.md`
```
  ---
  permalink: /zhou-resume/
  ---
```
- Browse to `username.github.io/fileofyourresume` or `username.github.io/permalink`

#### 9. Here is the demo 

![](https://github.com/igumiao/igumiao.github.io/blob/main/demo.gif)
![](https://i.imgur.com/suZs8LE.gif)


#### 10. More Resources

 - [Awesome Markdown Guide](https://www.markdownguide.org/basic-syntax/#links)
 - [Etter's book](https://www.amazon.ca/Modern-Technical-Writing-Introduction-Documentation-ebook/dp/B01A2QL9SS)
 - [GitHub Page Docs](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll)
 - [Jekyll Docs](https://jekyllrb.com/docs/)
 - [Git Command Guide](https://www.freecodecamp.org/news/10-important-git-commands-that-every-developer-should-know/)


----------------------
## Authors and Acknowledgments

This project uses [*The Cayman theme*][Caymanlink]

README was created using [readme.so](https://readme.so)

Maintained by [@igumiao](https://www.github.com/igumiao)







----------------------
## FAQ

#### Question 1. Why is Markdown better than a word processor?

Markdown is easy to learn and read. It's also easy to convert to HTML than word processor.

#### Question 2. Why is my resume not showing up?

You can try copy `_config.yml` , `Gemfile`, and `Gemfile.lock` from `/myresume` to your main repository (`username.github.io`). Find more information at [troubleshooting](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/troubleshooting-jekyll-build-errors-for-github-pages-sites)




[markdownlink]:<https://www.markdownguide.org/basic-syntax/#links>
[githublink]: <https://github.com/>
[gitdownload]: <https://git-scm.com/downloads>
[jekyllinstall]: <https://jekyllrb.com/docs/installation/>
[Caymanlink]:<https://github.com/pages-themes/cayman>
