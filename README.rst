-*- restructuredtext -*-

rapidsms-example-project
========================

This is an example of a RapidSMS project, as it might be deployed
in-country. When development settles down a bit, the rapidsms package
can be bundled into a deb, rpm, .tar.gz (or whatever), and installed
into site-packages. For now, it is a submodule.



Install
-------

Clone and rename project::

    $ git clone git://github.com/caktus/rapidsms-example-project.git rapidsms-project
    $ cd rapidsms-project
    $ git mv example_project/ myproj
    $ git commit -m "rename project"

Add rapidsms-core-dev as git submodule::

    $ git submodule add git://github.com/rapidsms/rapidsms-core-dev.git myproj/submodules/rapidsms
    $ git commit -m "add rapidsms submodule"

rapidsms-core-dev also contains submodules of its own, so init and update those as well::

    $ cd myproj/submodule/rapidsms
    $ git submodule init
    $ git submodule update

Now just syncdb and start the server::
    
    $ ./manage.py syncdb
    $ ./manage.py runserver

Visit http://localhost:8000/ in your browser.