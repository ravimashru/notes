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
