# Finding a WordPress plugin and adding it to composer.

+ There's a great site called [wpackagist.org](https://wpackagist.org/) (a spin on the [packagist.org](https://packagist.org/) name) where you can search for any free wordpress plugin and add it through composer.
+ Let's make an example. We want to install Yoast SEO on the blog.
+ Go to wordpress.org/extend/plugins and search for Yoast SEO. Once you've found the desired plugin click it and locate the slug of the plugin in the url like so:

![](http://puu.sh/puy1o/5b691af3d1.png)

+ Copy the slug into [wpackagist.org](https://wpackagist.org/)'s search field and hit **"Search"**.
+ Now you'll be presented with this view.
![](http://puu.sh/puyaP/2b571917a2.png)
+ If you just want the latest version, just click the last tag to the right. In our case it's **3.3.1**. 
	+ However, if you're looking for a specific version and it's not the latest 3 versions click the **...** to view all versions.
+ Once you've clicked on a version, you'll be presented with this view:
![](http://puu.sh/puylC/909bb9ee81.png)
+ This is the string you need to add to your composer.json file. Now copy and paste it (in this example's case **"wpackagist-plugin/wordpress-seo": "3.3.1"**), and paste it into your composer file wherever you see fit.

If you've already added a plugin in there before, a good idea could be to group the plugins after each other like this:

```
...
	"require": {
		"php": ">=5.4",
		"johnpbloch/wordpress": "4.3.1",
		"vlucas/phpdotenv": "^2.0",
		    
		"wpackagist-plugin/Akismet": "^3.1.5",
		"wpackagist-plugin/wp-polls": "2.72",
		"wpackagist-plugin/wordpress-seo": "^2.3.5",
		
	},
...
```

Run **composer install** or **composer update** and wait for it to load. If all worked well, you should be up and running! :rocket: