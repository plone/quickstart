
==========================
Developer Quickstart Guide
==========================


installation
------------

-  prereqs
-  default: unified installer

what we’ll create
-----------------

-  explain the case study for the project (conference site)

creating an add-on for plone
----------------------------

::

   - pip install plonecli
   - plonecli create addon
   - cd addon

-  run buildout
-  start instance
-  create plone site
-  install package

create a simple browserview
---------------------------

-  python: create the view class
-  pt: create the template

creating a content type with dexterity
--------------------------------------

-  what is a content type?
-  create a talk content type
-  from inside our addon: ``plonecli add content_type``
-  run buildout
-  restart and install package
-  add fields with zope schema

   -  simple set first, widget, permission and fieldset
   -  directives, mode, vocabularies, … later?

create a view for our content type
----------------------------------

create a browserview to list the talks
--------------------------------------

-  query of all ‘talks’ ct and show them as a list in a view
-  use plone.api to query the catalog for talks

add a behavior
--------------

-  reusable field for plone ct’s and talk ct
-  find a good use case (show on front page - featured item)

more
----

-  view that integrates featured items (for a specific amount of time),
   talks and twitterfeed on homepage
-  view that shows jokes from an api
-  adjust an existing plone ct
-  reuse event summary (plone existing stuff) inside your own views
-  add a js and css file via the resource registry
-  add a PCP configlet for your own CT (talk submission enabled)
-  adjust an plone setting and where to find them (like enable self_reg
   in chapter user generated content)