dumpaddress
===========

Python 3.3+ Supported. No Python 2.x. Sorry.

Command line tool for extracting addresses like urls and email addresses from any text file.
Uses the right method for the job:
----------------------------------
* Emails are extracted using string processing instead of regular 
  expressions due to the complexity of RFC 5822.
* URLs are extracted using a very well designed regex. 
* Links are extracted by parsing the href attribute of <a> tags.
  You can also supply a value to prepend urls.

Installation
------------
getum isn't in pypi just yet:

1. git clone git@github.com:indymike/dumpaddress.git
2. cd dumpaddress
3. pip3 install .


Usage
-----
**$ dumpaddress --help**

*Gets a list of commands*

**$ dumpaddress links --help**

*Gets help for links command*

**$ dumpaddress urls somefile.txt**

*returns a list of urls contained in somefile.txt.*

**$ dumpaddress emails somefile.txt**

*returns a list of email addresses*

**$ dumpaddress emails somefile.txt >emails.txt**

*saves all of the emails in somefile.txt in emails.txt*

**$ dumpaddress links somefile.html**

*returns a list of unique links from file*

Notes
-----
* This was written to try out the excellent click command line
  framework (http://click.pocoo.org/3/).  
* Python 3 only. This does not support Python 2x. Really, let's
  move on to Python 3 already. It's really worth it.
* Regular Expressions are useful when they work, but can create 
  very subtle failures. The URL probably has more than one way it 
  will fail to get urls, but it works well enough.
* email_regex works pretty well. email works a little better but is 
  slower.

Known Issues
------------
* link extraction just prepends whatever prepend value you give it.
  It does not currently check if there is an existing domain.

License
-------
This application is licensed under the BSD License.

Authors
-------
* Mike Seidle -- http://www.github.com/indymike
