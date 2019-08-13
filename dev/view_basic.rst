==============================
Creating a simple browser view
==============================

..  note::

  contents:

  - zcml: register a view
  - python: create the view class

    - Return "Hello World" in Python

  - pt: create the template generate html


.. sidebar:: Get the code!

    Get the code for this chapter (:doc:`More info <code>`):

    ..  code-block:: bash

        git checkout view


In this part you will:

* Register a view that can be opened in the browser
* Create and use a template for the view
* Create and use a python class for the view


.. _view-zcml-label:

Register the browser view in zcml
---------------------------------

Before writing the talk view itself we step back and
have a brief look at views and templates.

A view in Plone is usually a :py:class:`BrowserView`.
It can hold a lot of cool python code but we will first focus on the template.

Edit the file ``browser/configure.zcml`` and
register a new view called *training*:

.. code-block::xml
   :linenos:
   :emphasize-lines: 20-25

    <configure
      xmlns="http://namespaces.zope.org/zope"
      xmlns:browser="http://namespaces.zope.org/browser"
      xmlns:plone="http://namespaces.plone.org/plone"
      i18n_domain="ploneconf.site">

      <!-- Set overrides folder for Just-a-Bunch-Of-Templates product -->
      <include package="z3c.jbot" file="meta.zcml" />
      <browser:jbot
        directory="overrides"
        layer="ploneconf.site.interfaces.IPloneconfSiteLayer"
        />

      <!-- Publish static files -->
      <browser:resourceDirectory
        name="ploneconf.site"
        directory="static"
        />

      <browser:page
        name="training"
        for="*"
        template="templates/training.pt"
        permission="zope2.View"
        />

    </configure>

.. _view-pt-label:

Create a page template for the browser view
-------------------------------------------

Add a file ``browser/templates/training.pt``

.. code-block:: html

    <h1>Hello World</h1>

* Restart Plone and open http://localhost:8080/Plone/@@training.
* You should now see "Hello World".

You now have everything in place to learn about page templates.

..  note::

   The view ``training`` has no python class registered for it but only a template.
   It acts as if it had an empty python class inheriting from ``Products.Five.browser.BrowserView``
   but the way that happens is actually quite a bit of magic...

.. _view-py-label:

Create a view class in python for the browser view
--------------------------------------------------

Now we are going to enhance that view so that it will have
some python code, in addition to a template.
We will need to adjust our view registration in the zcml:

``browser/configure.zcml``

.. code-block:: xml
    :linenos:
    :emphasize-lines:  8

    <configure xmlns="http://namespaces.zope.org/zope"
        xmlns:browser="http://namespaces.zope.org/browser"
        i18n_domain="ploneconf.site">

        <browser:page
           name="training"
           for="*"
           class=".training.TrainingView"
           template="templates/training.pt"
           permission="zope2.View"
           />

    </configure>


Add a file ``browser/trainings.py``

We are adding a file called :file:`training.py` in the :file:`browser` folder.

:file:`browser/training.py`

.. code-block:: python
    :linenos:

    from Products.Five.browser import BrowserView

    class TrainingView(BrowserView):

        def the_title(self):
            return u'A list of great trainings:'

