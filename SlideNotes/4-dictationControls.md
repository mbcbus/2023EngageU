# Dictation Controls
Demo of a proof of concept file requiring hands free FileMaker usage

## Demo Points
- Activate and Deactivate the microphone
- Voice commands
- Speech-to-text dictation
- Text expansion
- Audible feedback

## Special Considerations
- Mostly everything here revolves around MacOS accessibility features. 
- Dragon Naturally Speaking, a popular dictation program, was discontinued for MacOS.
- The demo file for this will not be attached here, but specific code is shared below to help you.

## Sample Code
### Activate Voice Commands (MacOS Ventura and Above) via Perform Applescript
```
do shell script "open -b com.apple.systempreferences " & ¬
	"/System/Library/PreferencePanes/UniversalAccessPref.prefPane"

tell application "System Events"
	tell its application process "System Settings"
		repeat until UI element 4 of group 1 of scroll area 1 of group 1 of ¬
			group 2 of splitter group 1 of group 1 of window "Accessibility" exists
			delay 0.1
		end repeat
		click UI element 1 of group 3 of scroll area 1 of group 1 of group 2 ¬
			of splitter group 1 of group 1 of window "Accessibility"
		repeat until checkbox "Voice Control" of group 1 of scroll area 1 of group 1 of group 2 of splitter group 1 of group 1 of window "Voice Control" exists
			delay 0.1
		end repeat
		click checkbox "Voice Control" of group 1 of scroll area 1 of group 1 of group 2 of splitter group 1 of group 1 of window "Voice Control"
		
	end tell
end tell

tell application "System Settings" to quit
```

### Deactivate Voice Commands via Perform Applescript
```
do shell script "open -b com.apple.systempreferences " & ¬
	"/System/Library/PreferencePanes/UniversalAccessPref.prefPane"

tell application "System Events"
	tell its application process "System Settings"
		repeat until UI element 4 of group 1 of scroll area 1 of group 1 of ¬
			group 2 of splitter group 1 of group 1 of window "Accessibility" exists
			delay 0.1
		end repeat
		click UI element 1 of group 3 of scroll area 1 of group 1 of group 2 ¬
			of splitter group 1 of group 1 of window "Accessibility"
		repeat until checkbox "Voice Control" of group 1 of scroll area 1 of group 1 of group 2 of splitter group 1 of group 1 of window "Voice Control" exists
			delay 0.1
		end repeat
		click checkbox "Voice Control" of group 1 of scroll area 1 of group 1 of group 2 of splitter group 1 of group 1 of window "Voice Control"
		
	end tell
end tell

tell application "System Settings" to quit
```

### Speak a String of Text via Applescript
```
say "Whatever is in quotes will be spoken..."
```