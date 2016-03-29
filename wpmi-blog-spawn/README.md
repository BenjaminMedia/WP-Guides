#Spawn Blog in WPMI

1. Go to WPMI control panel
2. Login with credientials
3. go to "Create Blog"
4. Fill out the required fields
  5. Blog Name
  6. Blog URI
  7. Tag
  8. Server
  9. Git Repo
  10. Git Branch
  11. Git Tag
12. Press save new blog
  13.  A blog is added to a queue, so it might not be created immediately.
13. Go to logs
14. Wait & refresh the page until you see that a blog has been created.
15. SSH to the server (using the Terminal) with ```ssh forge@SERVERIPGOESHERE```
  16. If you're not sure which IP to login to, check which server you spawned the site on, after that, go to KYUP.com and login.
  17. Find the server name, and find the IP there.

> [WE SHOULD ADD THIS INTO WPMI] — alt domains to conf files.
18. using terminal commands go to ```/etc/nginx/sites-enabled/```
  19. ```cd /etc/nginx/sites-enabled/```
20. use ```ls``` to see a list of config files you can edit
21. use ```vim``` to open the file (ex. ```vim sitename.here```
22. snippet of sitename.here:
23. add a staging domain to `server_name`.
  24. like this: `server_name sitename.here /* CHANGES —> */ sitenam.interactives.dk`.
  25. example:
26. save the config file without restarting the server by running `sudo nginx -s reload`.
  27. if an error occurs like: `sudo: unable to resolve host c17308`. Send us a mail.
28. 

```` sitename.here
server {
listen 80;
server_name sitename.interactives.dk sitename.here;
root /home/forge/frutimian.no/public;

...
````