Creating an add-on for plone
----------------------------

::

   $ python3.7 -m venv quickstart
   $ cd quickstart
   $ source bin/activate
   $ pip install plonecli
   $ plonecli create addon ploneconf.quickstart
   $ cd ploneconf.quickstart
   $ pip install -r requirements.txt
   $ ./bin/buildout

-  start instance
-  create plone site
-  install package
