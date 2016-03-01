# known-install-on-uberspace
a (very) simple instruction to install known on an uberspace account

# What is "known"? [It's a blogging software](https://withknown.com/).

I assume you have an account for [uberspace](https://uberspace.de/) and know how to log in to you account with an [ssh client](https://duckduckgo.com/?q=ssh+client). (If not, that is really easy!)

First, some optional steps when you are using a (sub-)domain.

- log into your uberspace shell
- add the new domain to your uberspace account do
- `uberspace-add-domain -d [domainname] -w`
  ([here is some documentation](https://wiki.uberspace.de/domain:verwalten) in german)
- log into your domain registrar and add these subdomains with the IP address into your [zone file](https://en.wikipedia.org/wiki/Zone_file)
- activate zone file 

   (these two steps vary wildly in detail, depending on your domain registrar)
 
The installation itself:

- log into your uberspace shell
- `cd /var/www/virtual/[username]/`
- `wget https://github.com/idno/Known/archive/v0.9.0.4.zip`
(go to [github](https://github.com/idno/Known/releases) to get the latest release link)
- `unzip v0.9.0.4.zip`
- `mv Known-0.9.0.4/ [domainname]`
(or copy everything into your html folder if you use no seperate domain)

- log into your adminer interface
- create a new database called [username]_[dbname]

- wait until subdomains comes alive
- browse to [domainname] or [username].[servername].uberspace.de
- press button 'Let's get started' & 'Hooray! Let's get you set up.'
- name your site
- MySQL settings:
  * database name: [username]_[dbname]
  * username: [username]
  * password: [look up in .my.cnf in your user home in your uberspace shell]
  * server name: localhost
- upload dir (leave default): /var/www/virtual/[username]/[domainname]/Uploads/
- press button: 'Onwards!'
- input the information for your new account
- input the information for your profile 

__Congratulations__. Your have a running known website.

---
please send pull request if you have enhancements.

also on (http://known.matthias.welling.io/2016/how-to-install-known-in-your-uberspace)
