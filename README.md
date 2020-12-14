# WinUI3Preview3_Problems_TextBox

This repository contains two solutions with sample code demonstrating a TextBox within a ContentDialog in both UWP and WinUI3 Desktop.

The UWP sample code works as expected - the TextBox within the ContentDialog allows the user to type text into it. 

The WinUI3 Desktop sample builds but the TextBox within the ContentDialog does not contain the text typed. 

This issue appeared in previous preview release.

----

**Describe the bug**

In WinUI3 Preview 3 Desktop, we are unable to type in text into the TextBoxes inside ContentDialogs with some exceptions.

More detailed observations and debugging below in the "Additional Context" section.

**Steps to reproduce the bug**
1. Clone our [WinUI3 Preview3 Problems TextBox repository](https://github.com/eleanorleffler/WinUI3Preview3_Problems_TextBox).
2. Go to the TextBoxWinUI folder.
2. Open the TextBoxWinUI solution.
3. Build and run with Debug x64.
4. Once the application is loaded, click the "Click me" button.
5. Without clicking or clicking away from or outside of the application window, start typing into the TextBox.
6. No characters should appear - unless actions described in the "Additional context" are performed.

**Expected behavior**
We expect text to appear within the textbox when typing. We expect to see the same behavior we saw in UWP. 

Build and run the TextBoxUWP solution inside the TextBoxUWP folder to see expected behavior.

**Screenshots**

Screenshot#1 - TextBox inside ContentDialog

**Version Info**

NuGet package version: 

[Microsoft.VCRTForwarders.140 1.0.6]
[Microsoft.WinUI 3.0.0-preview3.201113.0]

Targeting:
Target: Universal Windows
Target version: Windows 10, version 1809 (10.0; Build 17763)
Min version: Windows 10, version 1803 (10.0; Build 17134)

Windows app type:
| UWP              | Win32            |
| :--------------- | :--------------- |
| 		Yes 	   |  				  |

| Windows 10 version                  | Saw the problem? |
| :--------------------------------- | :-------------------- |
| Insider Build (xxxxx)              | 						 |
| May 2020 Update (19041)            | 						 |
| November 2019 Update (18363)       | 						 |
| May 2019 Update (18362)            | 						 |
| October 2018 Update (17763)        | 			Yes			 |
| April 2018 Update (17134)          | 						 |
| Fall Creators Update (16299)       | 						 |
| Creators Update (15063)            | 						 |

| Device form factor | Saw the problem? |
| :----------------- | :--------------- |
| Desktop            | 		Yes			|
| Xbox               | 					|
| Surface Hub        | 					|
| IoT                | 					|

**Additional context**

- When trying to type into the TextBox immediately, no characters appear.

- When trying to type quickly with many characters into the TextBox immediately, the text cursor seems to freeze up and not blink.

- However, after clicking away from or outside of the application window, we are able to type in a subset of characters into the TextBox. This subset includes: 
	- These characters which use the same 5 keys with and without the shift key: []{}'"\|`~
	- Backspace key works.
	- Characters created using the Alt key and numeric keypad (e.g. Alt-65 for "A").
	- Characters copied from elsewhere can be pasted into the TextBox.
