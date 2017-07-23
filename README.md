# how to jekyll

*holding back the puns hnnnggg*

## basic directories

The basic idea with Jekyll is that you should be able to do almost everything
with Markdown and SCSS, and have all of the HTML just pop into being, including
meta, dates, slugs, and all the other accoutrements. So you only need to care
about a few directories for daily use.

Those are:

- `_drafts`: For when you want to work and store but not reveal yet
- `_posts`: Where you do the dated content
- `_sass`: Where you put the fancy stylings

There is also some basic info in files in the root directory, namely:

- `_config.yml`: The most general site configuration.
- `index.html`: The landing page.

## finessing

The way Jekyll converts everything to HTML is through templating, using a
domain-specific language called Liquid. It's vaguely bash-like, but much more
sensible. If you think of it as some `if`s and some `for`s and some composable
incantations like `uppercase | split | do_something_else`, you'll be just fine
with it. Liquid goes inside HTML and will be filled in with things when the site
is generated.

This stuff goes on in two specific folders:

- `_layouts`: Liquid/HTML partials that are referenced in the YAML of every post
  in the top (the "YAML front matter"). So if you choose `layout: post`, the
  content gets put inside the `post` layout.
- `_includes`: These are partial snippets that are intended to be smaller and
  more general than specific layouts. The idea is that you can include them
  using a Liquid directive and build up your layouts with them.

### themes

I am informed by [Jekyll and co.](https://jekyllrb.com/docs/themes/) that themes
now normally have their own `_layouts`, `_includes`, and `_sass` folders. So
you'll need to make those to override those settings with your own. `¯\_(ツ)_/¯`
