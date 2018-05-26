# The API Stylebook ![](https://travis-ci.org/arno-di-loreto/apistylebook.com.svg?branch=master)

The [apistylebook.com repository](https://github.com/arno-di-loreto/apistylebook.com) contains the data and tools used to build the [API Stylebook](http://apistylebook.com). 
The API Stylebook aims to help API Designers to solve API design matters and build their API design guidelines by providing quick and easy access to selected and categorized resources.  
[More detail about the API Stylebook.](http://apistylebook.com/blog/the-api-stylebook)

# Repository structure
- api: Static files pushed to the [apistylebook-api repository](https://github.com/arno-di-loreto/apistylebook-api) on gh-pages branches along with the files generated by `builder`
- builder: Node module using `data` files to generate md files used by jenkins web site in `web` and the YAML and JSON files for the static API in `api`
- data: YAML files containing the API Stylebook data
- scripts: Scripts to build and deploy the API Stylebook website and API 
- web: Jenkins website pushed to the [apistylebook-web repository]() on gh-pages. Used the md files generated by `builder` 

# Contributing to the API Stylebook

You can contribute to the API Stylebook by sending PRs.

## Add a new styleguide 
To add a new styleguide, you need to create a new guideline file `some-company-new-guidelines-id.yaml` in `data/guidelines`.

```YAML
id: some-company-new-guidelines-id
title: New Guidelines
type: website
url: https://developer.somecompany.com/docs/guidelines/
company: Some Company
companyLogoUrl: /media/logos/some-company.png
companyUrl: https://developer.somecompany.com/
screenshotUrl: /media/screenshots/some-company-new-guidelines-id.png
date: 2016-01-22
reviewDate: 2016-09-01

topics:
  some-topic:
    - name: Some Section Name
      url: https://developer.somecompany.com/docs/guidelines/#some-section-name
      quote: A quote to find easily the topic in the section 
```

### Add a new topic
To add a new topic which was not already covered by an existing guideline, you need to add it to the `data/design/guidelines/topics.yaml` file.

```YAML
some-topic:
  category: Some Category
  name: Some Topic
  description: A description of this topic
```

# Tools used

Here's the list of tools used:

- [Bootstrap](https://getbootstrap.com/) to build easily a responsive website
- [Bootstrap TOC](https://afeld.github.io/bootstrap-toc/) for dynamic TOC sidebar
- [Anchor JS](http://bryanbraun.github.io/anchorjs/) to add links on H1, H2, H3 sections titles on posts
- [Font Awesome](http://fontawesome.io/) for icons
- [Jekyll](https://jekyllrb.com/) to build the static website apistylebook.com
- [Github Page](https://pages.github.com/) to host apistylebook.com and api.apistylebook.com
- [Travis CI](https://travis-ci.org/) to build and deploy apistylebook.com and api.apistylebook.com

# About Google Analytics

This website used Google Analytics with anomized IP and disabled cookies thanks to this post: https://medium.com/jaysquared-com/implement-google-analytics-without-cookies-to-comply-with-gdpr-eu-cookie-law-and-eprivacy-a345c0fe89d7