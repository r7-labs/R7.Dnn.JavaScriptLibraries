# About R7.Dnn.JavaScriptLibraries

R7.Dnn.JavaScriptLibraries is a collection of JavaScript libraries used across various R7 projects,
packaged as [DNN JavaScript Libraries](https://www.dnnsoftware.com/wiki/javascript-libraries).

## Usage note

Though you could reference main library files via DNN API (`dnn:JavaScriptLibraryInclude` skinobject or `JavaScript.RequestRegistration` call),
it won't allow you to reference other files (namely secondary scripts and CSS) which packaged along with the main script.

In this case, you could use generic [DNN Client API](https://www.dnnsoftware.com/wiki/client-resource-management-api) to reference such resources.
This approach have evident flaws, but could be still useful is some cases:

```asp
<%@ Register TagPrefix="dnn" Namespace="DotNetNuke.Web.Client.ClientResourceManagement" Assembly="DotNetNuke.Web.Client" %>

<dnn:DnnJsInclude runat="server" FilePath="~/Resources/Libraries/BlueimpGallery/02_33_00/js/jquery.blueimp-gallery.min.js" />
<dnn:DnnCssInclude runat="server" FilePath="~/Resources/Libraries/BlueimpGallery/02_33_00/css/blueimp-gallery-video.css" />
```