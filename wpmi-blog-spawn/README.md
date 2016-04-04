#Spawn Blog in WPMI

###1. Required Information
* WPMI Login
* Bonnier's KYUP.com login credientials
* SSH access to the servers (your SSH public key added to the servers)
* Accesss to the [Github Repo](https://github.com/BenjaminMedia/wp-blog-template).
* Contact Bonnier's AppTeam for access to this.


1. Go to WPMI control panel
2. Login with credientials
3. go to "Create Blog"
4. Fill out the required fields:
  5. **Blog Name** — only used in WPMI list view
  6. **Blog URI** — the URL eg. `sitename.here`
  7. **Tag** — the type of blog.
  8. **Server** — which Blog Server you would like to add the blog to.
  9. **Git Repo** — just enter `BenjaminMedia/wp-blog-template`.
  10. **Git Branch** — `master` unless it's a custom blog like 
  11. **Git** *(version)* **Tag** — get the [latest version](https://github.com/BenjaminMedia/wp-blog-template/releases) name.
  12. Press "save new blog".

13. The blog is now added to a queue, so it may not be created immediately.

13. Go to `logs`.
14. Wait & refresh the page until you see that a blog has been created.
15. SSH to the server (using the Terminal) with ```ssh forge@SERVERIPGOESHERE```
  16. If you're not sure which IP to login to, check which server you spawned the site on, after that, go to KYUP.com and login.
  17. Find the server name, and find the IP there.

18. using terminal go to ```/etc/nginx/sites-enabled/```

20. use ```ls``` to see a list of enable-sites files.

21. use ```vim``` to open the file you want to edit (in our case, we'll call ```vim sitename.here```)

22. snippet of `sitename.here`

	````
	server {
	listen 80;
	server_name sitename.here;
	root /home/forge/sitename.here/public;
	
	...
	````

23. add a staging domain to `server_name` after the main site name.

  	eg. `server_name sitename.here /* CHANGES —> */ sitenam.interactives.dk`.
  
	snippet of `sitename.here`
	
	```` sitename.here
	server {
	listen 80;
	server_name sitename.here sitename.interactives.dk;
	root /home/forge/sitename.here/public;
	
	...
	````

26. save the config file without restarting the server by running `sudo nginx -s reload`.

> if an error occurs like: `sudo: unable to resolve host c17308`. Just ignore it.
