Required Packages
===

Package | Version
------------ | -------------
python-cherrypy | 3.2.2
python-ldap | 2.3.10
python-jinja2 | 2.2.1
python-websockify | 0.5.1
numpy | 1.4.1
words |


Configuration
===

You can find the main configuration file at: `config/global.conf`. If you wish to use a `.ini` fromat, change all `:` to `=`. 

```
email    : The helpdesk/support email address that appears throughout the website
headnode : The URL of the OpenNebula XMLRPC API (recomended to use HTTPS)
badwords : Location of bad words file to strip out of the random VM name generator

auth.ldap_address : The URL of an LDAP server to convert FedID into real name (optional)
auth.ldap_basedn  : The basedn to lookup in LDAP (optional)

wshostname : The hostname where you are running websockify (for NoVNC)
wsport     : The port that websockify is running on
wscert     : The location of the SSL cert
wskey      : The location of the SSL key
wstokendir : A directory to store NoVNC tokens in

wsgi_enabled : Set to true if you want to lanch this application behind something like Apache
```


Launching 
===

To launch the webfrontend without Apache, run the following:

`python server.py`

And then navigate to:

`http://hostname:81/`

When running the webfrontend without Apache, you might have to manually launch websockify.

`/usr/bin/websockify -v PORT --cert=CERT --key=KEY --target-config=TOKENDIR`
