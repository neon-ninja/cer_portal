cer_portal
==========

Slim portal to integrate various cluster-related webpages into a single webpage.

The disparate webpages are pulled into the portal via an iframe and displayed under a central header and menu structure.

The state of the iframe, i.e. the loaded URL including query string and hash, is stored in the hash in the URL of the main page to enable bookmarking.
State changes to the iframe, caused by clicks on menu links from outside the iframe, by history changes using the browsers back and forward button, or by clicks on links of the page within the iframe are captured and stored.

To load pages into the iframe requested clicks on links outside of the iframe, or by using the browsers history, a new iframe is created every time and the old iframe is replaced with the new iframe. 
Just setting a new src element on the old iframe causes duplication of entries in the browser history (one for the main page, one for the newly sourced element in the iframe), and makes using the browser history a rather unpleasant experience.

All integrated webpages that need to be protected by Tuakiri/Shibboleth, are proxied through a "protected path" (/portal/auth/*). This configuration must be done in the proxy configuration of the hosting web server.
