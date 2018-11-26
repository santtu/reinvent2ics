======================================
 AWS re:Invent session to ICS scraper
======================================

This has been tested only with re:Invent 2018 interest pages.

Setup
=====

Run ``pip install -r requirements.txt`` either directly, or in a
virtualenv.

Using
=====

This script does not have access to your account (at least not nicely)
and since it contains some Javascript elements you first need to do
some manual work:

1. Go to your interest page
2. Open developer console (*View > Developer > Javascript console* on
   Chrome, for example)
3. Run the following javascript code (copy-paste into the javascript
   console): ``$('.expandSessionImg').click(); $(.'moreLink').click()``
4. Copy and paste the HTML directly (*File > Save* will not work) ---
   select *Elements* from the javascript console, click on the
   ``<html>`` element, right-click, select *Copy > Copy element*
5. Save the copied element into a file (use your favourite editor)

Now you can use the saved file as input to the ``scraper`` program in
this directory::

  ./scraper interest-page.html >calendar.ics

Finally, you can just import the ICS file into any calendar program
you want.


License
=======

Licensed under Apache License 2.0. See the ``LICENSE`` file for
details on the license.
