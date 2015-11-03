### DEPRECATED
**This guide repository has not been updated and is no longer correct for current Chef releases. It should only be used for historical context at this point.**

Django Quick Start CMS Demo Application 
=======================================

Very simple Django application that leverages the [Django CMS platform](http://django-cms.org/).

Requirements
============

* git
* python 2.6+
* virtualenv 1.5.1+
* pip 0.8.1+

Setup Instructions
==================

### Create a Virtualenv

    ~$ virtualenv ~/virtualenvs/django-cms
    ~$ source ~/virtualenvs/django-cms/bin/activate

### Clone the Code

    ~$ git clone https://github.com/opscode/django-quick-start-cms.git

### Install Required Pip Packages
    
    (django-cms):~$ cd django-quick-start-cms
    (django-cms):~/django-quick-start-cms$ pip install -r requirements.txt

### Bootstrap & Migrate Database

    (django-cms):~/django-quick-start-cms$ python manage.py syncdb --migrate --all
    
### Launch the Server

    (django-cms):~/django-quick-start-cms$ python manage.py runserver 0.0.0.0:8080

Setup Database Non-Interactively
================================

    (django-cms):~/django-quick-start-cms$ python manage.py syncdb --all --noinput
    (django-cms):~/django-quick-start-cms$ python manage.py createsuperuser --noinput --username=admin --email=admin@foo.com
    (django-cms):~/django-quick-start-cms$ export DJANGO_SETTINGS_MODULE=settings;python -c "from django.contrib.auth.models import User; u=User.objects.get(username='admin');u.set_password('foobar');u.save();"

License and Author
==================

Author:: Seth Chisamore (<schisamo@opscode.com>)

Copyright:: 2011, Opscode, Inc

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
