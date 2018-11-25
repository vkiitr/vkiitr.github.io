
### Start in 4 steps

1. Download or clone repo `git clone https://github.com/vkiitr/vkiitr.github.io.git`
2. Enter the folder: `cd /vkiitr.github.io`
3. Install Ruby gems: `bundle install`
4. Start Jekyll server: `bundle exec jekyll serve`

Access, [localhost:4000/](http://localhost:4000/)

### Deploy in Github pages in 2 steps

1. Change the variables `GITHUB_REPONAME` and `GITHUB_REPO_BRANCH` in `Rakefile`
2. Run `rake` or `rake publish` for build and publish on Github

---

### Using Rake tasks

* Create a new page: `rake page name="contact.md"`
* Create a new post: `rake post title="TITLE OF THE POST"`

---

### Demo and Download

[Demo](https://vkiitr.github.io/)
[Download](https://github.com/vkiitr/vkiitr.github.io/archive/master.zip)

![Preview](/screenshot.png)

---

Enjoy :yum:
