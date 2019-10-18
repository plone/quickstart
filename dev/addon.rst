Creating an add-on for plone
----------------------------

- install plonecli and create an addon with it

::

   mkdir quickstart
   cd quickstart
   python3 -m venv .
   source bin/activate
   pip install plonecli
   plonecli create addon ploneconf.quickstart
     - answer all questions
   deactivate

- inside the addon install the requirements
   
::

   cd ploneconf.quickstart
   python3 -m venv .
   ./bin/pip install -r requirements.txt
   ./bin/buildout

-  start instance

::

   ./bin/instance
      
-  create plone site
-  install ploneconf.quickstart package
