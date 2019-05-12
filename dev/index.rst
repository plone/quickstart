
==========================
Developer Quickstart Guide
==========================


What is Plone?
--------------

https://training.plone.org/5/mastering-plone/what_is_plone.html


what we’ll create
-----------------

-  explain the case study for the project (conference site)



installation
------------

-  system-requirements
-  should we use the unified installer or the package-buildout created by plonecli?



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


create a browserview
--------------------

- zcml: register a view
- python: create the view class

Return "Hello World" in Python

- pt: create the template generate html




creating a content type with dexterity
--------------------------------------

-  what is a content type?
-  create a talk content type
-  from inside our addon: ``plonecli add content_type``
-  run buildout
-  restart and install package
-  add fields with zope schema

   -  simple schema first
   -  then: custom widget, field-permissions and fieldset
   -  simple vocabularies


create a view for our content type
----------------------------------

- zcml: register view
- python: write view that returns data from template  as json
- pt: write view that displays data from type


create a browserview to list the talks
--------------------------------------

-  query of all ‘talks’ ct and show them as a list in a view
-  use plone.api to query the catalog for talks


add a behavior
--------------

-  reusable field for plone ct’s and talk ct
-  ``featured``: "Show on front page"
-  Maybe: Add a index for that field?


more
----

-  Frontpage-View that shows featured items (for a specific amount of time)
   talks and twitterfeed on homepage
-  view that shows jokes from an api
-  interacting with content: create, edit, move, publish)
-  adjust an existing plone ct
-  reuse event summary (plone existing stuff) inside your own views
-  add a js and css file via the resource registry
-  add a PCP configlet for your own CT (talk submission enabled)
-  adjust an plone setting and where to find them (like enable self_reg
   in chapter user generated content)
-  add a endpoint? Good usecase needed since most things can be done with existing endpoints.


Parts from Mastering-Plone that we should use:

- https://training.plone.org/5/mastering-plone/dexterity_3.html
- https://training.plone.org/5/mastering-plone/views_1.html
- https://training.plone.org/5/mastering-plone/views_2.html
- https://training.plone.org/5/mastering-plone/views_3.html
- https://training.plone.org/5/mastering-plone/behaviors_1.html
- https://training.plone.org/5/mastering-plone/api.html
- https://training.plone.org/5/mastering-plone/events.html
