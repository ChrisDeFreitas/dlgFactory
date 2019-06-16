# dlgFactory

This is a very early version of the concept.  I've used and expanded it much over the years.  A good example of its usage is in the <a href="https://github.com/ChrisDeFreitas/Electron-FolderView">Electron Folder View</a> application.

The basic idea is to provide core functionality to create HTML controls on a webpage.  This was put together before the advent of Web components and the popularity of React Components.  This solution evolved to supply primitive functions, allowing the library functionality to be dynamically mixed based on the project and developer needs (see <a href="https://github.com/ChrisDeFreitas/Electron-FolderView/blob/master/lib/dlgFactory.js">dlgFactory.tac2()</a>).  This contrasts with a component set like Google's <a href="https://material.io/develop/">Material Design Components</a>, which creates fixed components that perform specific tasks.

An example of using primitive functions to build complex functionality based on application needs is the pathBar in Electron Folder View.  It allows the Windows file system to be traversed simply: <a href="https://github.com/ChrisDeFreitas/Electron-FolderView/blob/master/scrnshots/scrn06%20-%20pathBar.jpg">a very old screen shot</a>, and <a href="https://github.com/ChrisDeFreitas/Electron-FolderView/blob/master/lib/pathBar.js">source code</a>.

My personal favorite component (because of its functionality) is the Rename dialog: <a href="https://github.com/ChrisDeFreitas/Electron-FolderView/blob/master/scrnshots/scrn09%20-%20Rename%20dialog.jpg">screen shot</a>, and <a href="https://github.com/ChrisDeFreitas/Electron-FolderView/blob/master/lib/dlgRename.js">source code</a>.

Feel free to use and modify.

## Features
- dialog boxes: z-index=1000, drag to position, close button, dynamically managed, simple css  

- dlgFactory.msg(message, title)  
	-- message can be html or text

- dlgFactory.bigText(message, title)  
	-- assume message is string (not html)  
	-- dlg content: <textarea>message</textarea>

- dlgFactory.create(options)  
		-- general purpose entry point
```Javascript		
var options = {
	title:	(title===undefined ?"Message" :title),
	body: 	(html or text),
	focusId: (null  or provide element id eg '#inpDelay'),	//element to focus on show
	left: 	(options.left ?options.left :'50vw'),
	top:		(options.top ?options.top :'40vh'),
	height:	(options.height ?options.height :'auto'),
	width:	(options.width ?options.width :'auto'),
	buttons:{	//not required
		default: 'Save',	//caption of button to select when user presses Enter key
		Save: function(dlg, btnCaption){	//dlg = div container of dlg
			alert(111)
		}
	}
}
```			

## Thanks To
https://developer.mozilla.org/


Chris  
chrisd@europa.com
