Title: Whoops.
Date: 2006-04-10 23:01:05
Category: general
Slug: whoops
Author: Russell Neches
Tags: code
Summary: 


In creating a new database for Rails hacking, I accidentally reset the
password for my Typo database. After much scrutiny, it was impossible to
tell that the problem was caused by Typo no longer being able to log
into its database. There was no connection error in any of the logs
(that I could find after days of looking).

I only noticed after I tryed to log into the database manally to inspect
the tables for damage. So, not only did Typo not generate an error, but
it kept serving cached pages without comment.

Dear Typo: Work or don't work. Half working is worse than broken.
