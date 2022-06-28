---
layout: default
title: Markdown Profile Page
---

[DRAFT]

# Getting Started With GitHub Pages using Markdown! 🏁

If you reading this blog means you want to create minimal portfolio or profile without thinking more around designing but should be more professional and small, compact & easy to implement without any setup, learning any new language. If you are the one who don't like to code around HTML tags, CSS files or JS. If you are backend engineer like me :) and want good profile page without worrying about the frontend language.

> You are always welcome to raise pull request to improve this blog.

GitHub provides each user domain of its github username followed by `github.io` where your profile is hosted as a website. there are multiple ways you can create your portfolio. You can use any existing framework, language, tools, forking existing repositories and updating as required. This post will focus on how can you write only your portfolio content using markdown and let github take care of rest.

Prerequisite: [How to setup your repository to act as website?](https://github.com/themayurkumbhar/themayurkumbhar.github.io/edit/markdown-profile-page-post/posts/getting-started.md#setting-up-changes-in-github)

Once you have basic repository setup ready you can follow along.

## Why to use markdown? 🤔

Markdown is most widely used for documentation purpose. Most of developers use this as day to day work in documenting either APIs, WiKi or repository README.md files. This enables best practices and standard structure present in markdown to write portfolio in better format. Also developers are mastered in writing markdown (if you are not, strongly suggest to practice documentations using markdown).

> 💡 Quick understanding of [MarkDown](https://www.markdownguide.org/basic-syntax/)!

## Let's Get Started -

### Repositroy Structure Layout 🧱

```text
.
├── Readme.md
├── _config.yml
├── _includes
│   ├── about-me.md
│   ├── contact.md
│   ├── education.md
│   ├── posts.md
│   └── professional.md
├── index.md
└── posts
    └── getting-started.md

```

### Understanding different files in Repository 📚

#### 1. [index.md](./../index.md) -

  This is the main file which used as root for the website. When someone hits your profile url this is the first page that gets loaded, which also called as "Landing Page"

* You can have a single page website where you can add all the profile data in the same file.
* Or you can choose the separate the files in multiple folders and update specific sections as and when required.

> 💡 We will discuss the multiple files approach in this post.

* [index.md file] looks like this:

```markdown
  ---
  layout: default
  ---

  {% include about-me.md %}

  {% include professional.md %}

  {% include education.md %}

  {% include contact.md %}

  {% include posts.md %}

```

* Layout part defines which layout to use while rendering index file.
* Syntax `{% include filename.md %}` imports the files in your index file and expands the contents to fit in a single file.
  * github before generating website first imports all the contents and then renders the files conetent as HTML/CSS.

#### 2. [\_config.yml](../../_config.yml) -

  This file used to configure the configuration parameters which can be used by the github website generator [Jekyll](https://github.com/daattali/beautiful-jekyll/blob/master/_config.yml). We will see the some basic required configurations which will enable us to generate the portfolio website.

* [config file](../../_config.yml) looks like below:

  ```yaml
  title: <Title of your website>
  description: <discription of your wesite>
  theme: jekyll-theme-slate #which theme you want to select for your website*
  relative_links: #this is true to enable your posts relative path to website
    enabled: true
    collections: false
  plugins:
    - jekyll-relative-links #enable your posts links relative path to website
    - jekyll-default-layout #you can keep default or you can create new layout and add as layout here
  ```

* You can select a theme from the list of jekyll themes [HERE](http://jekyllthemes.org/)

> 💡 This website is generated using a theme called [jekyll-theme-slate](https://github.com/pages-themes/slate)

#### 3. [\_includes](../_includes) -

  This **folder** contains all the separate MarkDown files which are part of the portfolios and are broken down to specific contents of file, so they can be modified independently.

* Includes can contain any kind of data files which are logically separated from each other contents.
* You can distribute your contents as required in multiple files and then include them as and when required in different files/ index file.
* Example for [contact.md](../_includes/contact.md) file

```markdown
  ## 📇 [Connect with Me!](#contact)
  ✉️ [mailme@mail.com](mailto:mayur.kumbhar@outlook.com) &emsp; 📱 [+91-1234567890](tel:+911234567890)
```

#### 4. [\_posts](./) -

  This **folder** contains all your blog posts which are separated with each new MarkDown file. Once the blog post file is created you need to include that in your [posts.md](../_includes/posts.md) file to publish on your website.

* Always create a new file for each blog, include them only when ready to publish.
* You can also include diagrams/images/videos/code blocks in your blog.
* Example for including blog file in [posts.md](../_includes/posts.md):

  ```markdown
  ### [1. website title](../path/to/posts_file.html)
  ```
  
### Setting up changes in github ⚙️

  Once you are ready with your portfolio files, make sure then are committed and pushed to your github repository named `<your_github_username>.github.io`.
  
  Let's now set up your special repository to act as a website using github.

  1. Go to `Settings` on your repository
  2. Select `Pages` section, which will show you `Github Pages` 
  3. Now select drop-down `Source` and choose `master` branch to configure & hit `save`.
  4. Wait for a minute or two, you will get the link to your website
  5. Boom! Your website is ready!!! 🚀

> 💡 Bonus Fact: You can include HTML/CSS tags in your MarkDown file to have more control over customizations! 😎

---

   If you face any issues, need more details/information you can [reach out to me](mailto:mayur.kumbhar@outlook.com) anytime! Keep Learning! Keep Exploring! ✌
