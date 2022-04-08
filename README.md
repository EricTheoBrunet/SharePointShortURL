# SharePointShortURL

In this project I am sharing instructions and sample code to help you create short links using sharepoint.

### Use case
Véronique needs to include a link to a Microsoft Teams meeting invites in the corporate HR employee learning system. The system only accepts a maximum lenght of 100 characters. The Microsoft Teams meeting invite is well above 100 characters.

### Common approach 
Users will typically use a third party like https://bitly.com/

This approach may not be appropriate as you are sending trafic outside of your organization.

### Proposed solution
Host ASPX files using the shortest path possible on your SharePoint site and use a basic HTML technique to redirect users to the longer URL.  

### Requirements
* Read/Write access to a SharePoint file repository.

### Instructions
1. Make a local copy of the file [short-url.aspx](https://github.com/EricTheoBrunet/SharePointShortURL/blob/main/short-url.aspx) found in this repository.
1. Open the file using a basic text editor like Notepad on Windows or TextEdit on Mac.
1. Replace both *long-url* in the file with your long URL.
1. Set *redirect-delay* to 0. This is the number of seconds it will take before the redirect occurs. 
```
<html>
	<head>
		<meta http-equiv="refresh" content="redirect-delay; URL=long-url" />
	</head>
	<body>
		<p>If you are not redirected, <a href="long-url">click here</a>.</p>
	</body>
</html>
```
4. Rename the ASPX file to something meaningful, try to keep it as short as possible (this will inpact the length of your short URL).
1. Upload the ASPX file to you SharePoint. Try to keep the folder structure light and the folder names short. Exmaple: https://corporate.sharepoint.com/sites/HR/Learning/Redirect/short-url.aspx
1. Once uploaded click the file and you should be redirected to your long URL. If not, verify your code changes and make sure you only replaced the long-url.

Note: The file can only be edited locally on your computer and uploaded to SharePoint everytime you make a change.

### FAQ
The page gets redirected before I am able to grab the short URL.
* Temporarely set the *redirect-delay* to lets say 30, upload the new changes, click on the file where you will now have 30 seconds to grab the short URL. Once you have it, set back *redirect-delay* to 0 (or the value of your choise) and upload your file.  

### Found a bug?
Please take a look at [CONTRIBUTING.md](CONTRIBUTING.md#you-think-youve-found-a-bug) and submit your issue [here](https://github.com/EricTheoBrunet/SharePointShortURL/issues).


----


# Contributing to the project

We are always looking for the quality contributions! Please check the [CONTRIBUTING.md](CONTRIBUTING.md) for the contribution guidelines.

