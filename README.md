# proto.nieder.me

A simple [harp server](http://harpjs.com) setup for prototyping, set up for easy deployment to [GitHub Pages.](https://help.github.com/articles/creating-project-pages-manually/) 

***

_This implementation includes BuzzFeed’s [Solid CSS framework](http://github.com/buzzfeed/solid), as well as @niederme’s simple prototypes._

_This was forked from @jakemhiller’s [jh-harp-base](https://github.com/jakemhiller/jh-harp-base) and @emilybrick’s [gh-pages](https://github.com/emilybrick/prototypes/tree/gh-pages)._

***

# Usage Instructions

### Install

1. Clone or fork this repo
2. `cd` into the directory
3. Install harp: `npm install harp -g`
4. If you want to [deploy to a custom domain](https://help.github.com/articles/setting-up-a-custom-domain-with-github-pages/), you’ll need to edit the CNAME file. (If not, delete it.)

***

### Run the Harp Server on port 8000

	$	make run
    
	harp server _harp/ -p 8000

***

### Adding and Editing Files
Source files are in `./_harp/public`, and get compiled up two levels to the root. (This is a requirement for publishing to Github Pages, but is a bit confusing.)

To create a new file, duplicate the starter template, rename it and go nuts.

To update Solid:

	$	cd ./_harp/public/node_modules/bf-solid
	$	npm update

***

### Compile for Github Pages
Github pages have to be served out of the root folder, but Harp deletes the root on compile. So we will compile into a directory, and then move it to the root.

	$ 	make dev
	
	rm -Rf *.html
	rm -Rf ./css
	rm -Rf ./js
	harp compile ./_harp ./www
	mv -fv ./www/* ./
	rm -R ./www

***

### Add, Commit and Push

	$	git add .
	$	git commit -m "commit message here!"
	$	git push origin gh-pages

***
	
### Done!

	http://proto.nieder.me