# dlgFactory

This is a very early version of the concept.  I've used and expanded it much over the years.  A good example of its usage is in the <a href="https://github.com/ChrisDeFreitas/Electron-FolderView">Electron Folder View</a> application.

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
