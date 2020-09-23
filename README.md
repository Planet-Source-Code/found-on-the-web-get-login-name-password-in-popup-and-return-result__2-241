<div align="center">

## Get login name/password in popup and return result


</div>

### Description

How can I capture a login name and password in a popup window and then pass it onto the next page?

Found at: http://www.irt.org
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Found on the Web](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/found-on-the-web.md)
**Level**          |Unknown
**User Rating**    |4.0 (28 globes from 7 users)
**Compatibility**  |
**Category**       |[Windows](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/windows__2-80.md)
**World**          |[Java](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/java.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/found-on-the-web-get-login-name-password-in-popup-and-return-result__2-241/archive/master.zip)





### Source Code

```
initial.html:
<SCRIPT LANGUAGE="JavaScript"><!--
var loginname = '';
var loginpassword = '';
function windowOpen() {
  var myWindow=window.open('popup.html','windowRef','width=200,height=200');
  myWindow.location.href = 'popup.html';
  if (!myWindow.opener)
    myWindow.opener = self;
}
function go(url) {
  location.href = url + '?' + loginname + '&' + loginpassword;
}
windowOpen();
//--></SCRIPT>
<A HREF="javascript:go('nextpage.html')">go to next page</A>
popup.html:
<SCRIPT LANGUAGE="JavaScript"><!--
function returnDetails() {
  opener.loginname = document.myForm.loginname.value;
  opener.loginpassword = document.myForm.loginpassword.value;
  self.close();
}
//--></SCRIPT>
<FORM NAME="myForm">
Name: <INPUT TYPE="TEXT" NAME="loginname">
Password: <INPUT TYPE="PASSWORD" NAME="loginpassword">
<INPUT TYPE="BUTTON" VALUE="ENTER" onClick="returnDetails()">
</FORM>
nextpage.html:
<SCRIPT LANGUAGE="JavaScript"><!--
var start = location.search.indexOf('?');
var end  = location.search.indexOf('&');
var loginname = location.search.substring(start+1,end);
var loginpassword = location.search.substring(end+1);
alert('Name = ' + loginname + '\n' + 'Password = ' + loginpassword);
//--></SCRIPT>
```

