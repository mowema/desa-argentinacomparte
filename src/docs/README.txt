README
======

This directory should be used to place project specfic documentation including
but not limited to project notes, generated API/phpdoc documentation, or
manual files generated or hand written.  Ideally, this directory would remain
in your development environment only and should not be deployed with your
application to it's final production location.


Setting Up Your VHOST
=====================

The following is a sample VHOST you might want to consider for your project.

<VirtualHost *:80>
    DocumentRoot "/home/ricardo/Zend/workspaces/DefaultWorkspace7/brushfire/web/trunk/src/public"
    ServerName brushfire.local
    
    # This should be omitted in the production environment
    SetEnv APPLICATION_ENV local

    Alias /js/lib/ZendMax "/home/ricardo/Zend/workspaces/DefaultWorkspace7/brushfire/web/trunk/src/library/ZendMax/js/ZendMax"

    <Directory "/home/ricardo/Zend/workspaces/DefaultWorkspace7/brushfire/web/trunk/src/public">
        Options Indexes MultiViews FollowSymLinks
        AllowOverride All
        Order allow,deny
        Allow from all

        <FilesMatch ".less$">
            Header set Cache-Control "no-cache"
        </FilesMatch>
    </Directory>
</VirtualHost>