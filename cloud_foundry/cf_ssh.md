# SSH into CF App

## Error
```
$ cf ssh <app_name>
Error opening SSH connection: You are not authorized to perform the requested action.
FAILED
```

## Solution
* Enable SSH using `cf enable-ssh <app_name>`
* Restart app using `cf rs <app_name>`
