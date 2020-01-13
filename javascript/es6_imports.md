# ES6 Imports

```
import abc from "module-name";
```
This imports the `default` export of the module and assigns it to `abc`.
The name of the default export in `module-name` doesn't need to be the same as `abc`.

```
import { abc } from "module-name";
```
This imports the `abc` exports from `module-name`. Only items that have been exported 
from `module-name` can be imported like this.

To import and rename:
```
import { abc as def } from "module-name";
```

This syntax can be used to import the default export of `module-name` like this:
```
import { default as abc } from "module-name";
```

All the exports of a module can be imported into a single namespace like this:
```
import * as mn from "module-name";
```
All exports from `module-name` can then be accessed using `mn` as a namespace (e.g. `mn.abc`).
The default export can be accessed using `mn.default`.

> Note: this is equivalent to `mn = require('module-name')`.

It is also possible to merge the different formats:
```
import { abc, def as x } from "module-name";
import defaultExport, { abc, xyz } from "module-name";
import defExp, * as mn from "module-name";
```

