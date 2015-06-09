# Learn to npm!

This repository contains my learning notes of the [NodeSchool workshop "How to npm"](http://nodeschool.io/#workshoppers)


* If you get a .lock error trying to install a package, it may be caused by your previous installing packages in your home folder with `sudo`, i.e. as `root`. The fix is to change the owner of the `.npm` folder back to yourself instead of `root` with command `chown`

	```
	$ sudo chown -R my.user ~/.npm
	```

* If you install packages locally without first having them declared as dependencies in the `package.json` file, you are able to install them but will get an `extraneous` error, which indicates that the package is extraneous to the project. 

	* To remove an extraneous package, use the npm command `prune`

		```
		$ npm prune <name>
		```

	* To install a package as well as having it declared as a dependency in your `package.json` file at the same time, use the `--save` parameter when installing, or the `--save-dev` parameter to have it declared as a devDependency

		```
		$ npm install <package> --save
		```

		```
		$ npm install <package> --save-dev
		```