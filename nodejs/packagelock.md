# package-lock.json

Stores the exact versions of the packages installed. When you want to install these same exact versions again, you can use the `package-lock.json`.

To install these exact versions, use the command `npm ci` instead of  `npm install`.

### Example
You have express version `^4.15.3` in your `package.json` file and `4.15.3` was the version that was installed when you initially ran `npm install`, and that is what is stored in your `package-lock.json` file. Now there is also express version `4.25.6` available.

If you run `npm install` then express version `4.25.6` will be installed since the semantic version `^4.15.3` says "install the latest minor and patch release of major version 4". The same thing happens for all other dependencies in the `package.json` file. The `package-lock.json` file is then updated with the exact versions of the dependencies installed.

If you run `npm ci` then express version `4.15.3` will be installed, along with the exact versions of any other libraries that were installed when generating the `package-lock.json` file. The `package-lock.json` file will not change.