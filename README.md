ABOUT
-----
Instagallery allows you to pull recently tagged media from Instagram into your
Django project. 

QUICK START
-----------
Set Instagram client id in Django settings. You'll need to
[register](http://instagram.com/developer/register/) if you don't have a
client id from Instagram.

    INSTAGRAM_CLIENT_ID = 'foobar...'

Add instagallery to INSTALLED\_APPS

    INSTALLED_APPS = (
        '...',
        'instagallery',
    )

Install models

    $ python manage.py syncdb

Initiate daemons. For example with Supervisord:

    [program:foobar_get_instagram_images]
    command=/srv/foobar/bin/python /srv/foobar/project/manage.py get_instagram_images
    directory=/srv/foobar/project
    user=www-data
    autostart=true
    autorestart=true
    stdout_logfile=/var/log/supervisord/foobar.log
    redirect_stderr=true

    [program:foobar_check_instagram_images]
    command=/srv/foobar/bin/python /srv/foobar/project/manage.py check_instagram_images
    directory=/srv/foobar/project
    user=www-data
    autostart=true
    autorestart=true
    stdout_logfile=/var/log/supervisord/foobar.log
    redirect_stderr=true

LICENSE
-------
Copyright (C) 2014

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.

CREDITS
-------
A project by [Water.org](http://water.org/). For more than two decades,
Water.org has been at the forefront of developing and delivering solutions to
the water crisis. Founded by Gary White and Matt Damon, Water.org pioneers
innovative, community-driven and market-based solutions to ensure all people
have access to safe water and sanitation; giving women hope, children health
and communities a future. To date, Water.org has positively transformed the
lives of more than 1,000,000 individuals living across communities in Africa,
South Asia, Latin America and the Caribbean; ensuring a better life for
generations ahead.
