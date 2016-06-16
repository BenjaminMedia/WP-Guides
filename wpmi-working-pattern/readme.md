#The correct way to deploy to WPMI

Let’s say there’s something wrong with wp-grab-image.

You make some changes locally to wp-grab-image, and make it work, then you copy your changes to wp-grab-image’s git and commit the changes.
Then you deploy a new version of wp-grab-image, and update the wp-blog-template composer file with the latest version of wp-grab-image. Then you create a new version of the blog template and put that on the staging site. Make note of which wp-blog-template version the blog is currently using (so you can update it back to that version in case something is wrong.).

Make a backup of the blog’s database, and update the blog and see if the changes worked. If the changes did not work, and the staging site doesn’t work, give it the previous wp-blog-template version so that the staging site works again :)