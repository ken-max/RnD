---
layout: page
title: Making a New Project
---

Setting up a new project documentation page consists of four steps:

1. Make a new folder within the root directory named `_project_name`
2. Make a file in the root directory named `project_name.md` to serve
   as the project landing page
3. Add an `about.md` file within the project directory
4. Edit `_config.yaml` in the root directory to let the site know of
   the new project subfolder and landing page
   
To illustrate these steps, this guide will create documentation for a
sample project named `My Project` with the site's root directory
located at `~/RnD`


# Make a project folder

```bash
cd ~/RnD

mkdir _my-project
```

Notice the leading `_` in front of the name. This is necessary for
Jekyll to [properly handle and display the project
folder](https://jekyllrb.com/docs/collections/).

`_my-project` can contain any number of files and subdirectories, so
feel free to go wild.

# Make a landing page .md file 

A template for the landing file is located in the `_templates`
folder. Copy it into the root directory and rename it to
`my-project.md`.

```bash
cd ~/RnD
cp _templates/project_header_template.md my-project.md
```

Open `my-project.md` and edit the [front
matter](https://jekyllrb.com/docs/frontmatter/) so that it reflects
the name of your project and the text you want displayed on the
navigation bar at the top of every page.

Following our example, this:

```yaml
---
layout: page
title: [This is what is displayed on the navigation bar]
project: [project name here]
---
```
Turns into this:
```yaml
---
layout: page
title: My Project
project: my-project
---
```

This is the only change you will have to make outside of the
`_my-project` folder!

# Add an About.md for your project

Copy the `project_about_template.md` file located in the `_templates`
folder to your project folder, rename it to `about.md`, then edit the content as needed but
**leaving the front matter untouched**.

```bash
cd ~/RnD
cp _templates/project_about_template.md _my-project/about.md
```
The about file is intended to provide a quick summary of the
project. An [optional table of contents can also be made in the front
matter](#table-of-contents).

# Edit _config.yaml to add your project to the site

The last thing to be done in order for project documentation to become
visible is to add it to the site's `_config.yaml` document located in
the root directory. 

Two additions are made: 

1. Adding the project to the list of jekyll collections
2. Adding the landing page .md to the navigation bar

Opening `_config.yaml` you will see the following commented block of
text:

```yaml
######################################################################
# Add config info here!
# To add a new documentation topic of name DOC_TOPIC, extend both 'collections' and 'header_pages' with the following
#
#collections:
# [current collections info]
# DOC_TOPIC:
#  output:true
#
#header_pages:
# [current header_pages info]
# - DOC_TOPIC.md
#

collections:
 documentation:
  output: true

header_pages:
 - documentation.md


######################################################################
# Nothing below here should normally be messed with
######################################################################
```

Simply follow the specified format and append the project information
like so:

```yaml
######################################################################
# Add config info here!
# To add a new documentation topic of name DOC_TOPIC, extend both 'collections' and 'header_pages' with the following
#
#collections:
# [current collections info]
# DOC_TOPIC:
#  output:true
#
#header_pages:
# [current header_pages info]
# - DOC_TOPIC.md
#

collections:
 documentation:
  output: true
 my-project:
  output: true

header_pages:
 - documentation.md
 - my-project.md


######################################################################
# Nothing below here should normally be messed with
######################################################################
```

And that is it! You now have your own project documentation stub!
