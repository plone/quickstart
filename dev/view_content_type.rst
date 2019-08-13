=====================================
Creating a view for your content type
=====================================

.. note::

  - zcml: register view
  - python: write view that returns data from template
  - pt: write view that displays data from type

In this part you will:

* Register the view for our content type in zcml
* Create and use a template for the view
* Create and use a python class for the view


.. _view-ct-zcml-label:

Add the view in zcml
--------------------

We will need to add the registration of the view for our content type `Talk` in the zcml:

``browser/configure.zcml``

.. code-block:: xml
    :linenos:
    :emphasize-lines:  8

    <configure xmlns="http://namespaces.zope.org/zope"
        xmlns:browser="http://namespaces.zope.org/browser"
        i18n_domain="ploneconf.quickstart">

        ...

        <browser:page
           name="talk"
           for="*"
           class=".talk.TalkView"
           template="templates/talk.pt"
           permission="zope2.View"
           />

        ...

    </configure>

.. _view-ct-zcml-label:

Add the python class for the view
---------------------------------

Add a file ``browser/talk.py``

We are adding a file called :file:`talk.py` in the :file:`browser` folder.

:file:`browser/talk.py`

.. code-block:: python
    :linenos:

    from Products.Five.browser import BrowserView

    class TalkView(BrowserView):





