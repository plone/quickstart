=====================================
Creating a view to list all the talks
=====================================

.. note::

  -  query of all ‘talks’ ct and show them as a list in a view
  -  use plone.api to query the catalog for talks

In this part you will:

* Register a view that lists all the talks

.. _view-zcml-label:

Adjust the configuration of the view in zcml
--------------------------------------------

Now we are going to enhance that view so that it will have
some python code, in addition to a template.
We will need to adjust our view registration in the zcml:

``browser/configure.zcml``

.. code-block::xml
    :linenos:
    :emphasize-lines: 8

    <configure xmlns="http://namespaces.zope.org/zope"
        xmlns:browser="http://namespaces.zope.org/browser"
        i18n_domain="ploneconf.site">

        ...

        <browser:page
           name="training"
           for="*"
           class=".training.TrainingView"
           template="templates/training.pt"
           permission="zope2.View"
           />

        ...

    </configure>


Add a file ``browser/trainings.py``

We are adding a file called :file:`training.py` in the :file:`browser` folder.

:file:`browser/training.py`

.. code-block::python
    :linenos:

    from Products.Five.browser import BrowserView

    class TrainingView(BrowserView):

        def the_title(self):
            return u'A list of great trainings:'

