# Open random note from Apple Notes

Using AppleScript:

```applescript
tell application "Notes"
	
	set total to the count of notes
	set randomIndex to (random number from 1 to total)
	set rnote to the item randomIndex of notes
	show rnote
	
end tell
```

Exclude notes from specific folders:

```applescript
tell application "Notes"
	
	set total to the count of notes
	
	set randomIndex to (random number from 1 to total)
	set rnote to the item randomIndex of notes
	set fldr to container of rnote
	
	set excludeFolders to {"Personal", "04 Archive"}
	
	repeat until name of fldr is not in excludeFolders
		set randomIndex to (random number from 1 to total)
		set rnote to the item randomIndex of notes
		set fldr to container of rnote
	end repeat
	
	show rnote
	
end tell
```
