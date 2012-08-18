#Getting Started

## Welcome to the Windows Windows Azure Active Directory Preview Demonstration Application

This application has been written to provide you with a quick and easy way to set up your first application that connects seamlessly to Windows Windows Azure Active Directory. This demonstration application, written to run inside of Azure WebWorker role, will provide you with glipses in to the Preview release of two great technonologies described below. We've released all of the source code for this running example in GitHub under an Apache 2.0 license, so feel free to clone (or even better, fork!) and get this running in your own Vistual Studio environment.

##The Technologies In This Demo

This website will demonstrate the following technologies from the Windows Azure Active Directory from Microsoft:

- Web Single Sign-In (SSO)
- Access to Windows Azure Active Directory through a RESTful Graph API


### Windows Azure Active Directory WebSSO Preview

With Windows Azure Active Directory WebSSO, you will have the ability to seamlessly intergrate your application in to your customer's existing identity platform, while allowing them to use the same credentials they use in the office and online.

### Windows Azure Active Directory Graph API Preview

With Windows Azure Active Directory Graph API, you will have the ability to build data driven applications using a REST based API. You can use this REST API to query your customer's data, navigate relationships within their directory, and customize your applicaitons based on this data.

### Important Note About The Preview

#### API Changes From The Preview Release

This is a Preview release of the service, which means there may be changes to the content of this application as well as the structure and functionality of the associated APIs.

At this time, Windows 8 is not supported when running the PowerShell scripts. We will fix this in the future. Please use Windows 7 or Windows Server 2008 R2.

#### Things We Know We Need To Work On

As you use the demo application and code samples, you’ll experience a few issues that we are working on fixing but want to call out so that you can get up to speed faster.

##### Tenants Using ISV Application Must Use PowerShell to Authorize ISV Application

During this Preview release, we rely on the Microsoft Online Services Module for Windows PowerShell (updated for this Preview release) in order to allow for an ISV application to access the Graph API of the tenant who wishes to use the application, as well as for those tenants that wish to use SSO with their existing credentials for the ISV application.

We have created a PowerShell script that automates much of this work for the tenant in our documentation samples, but we are aware of the limitation of this approach and are working to provide a graphical authorization interface in the next release.

##### Audience URI varies based on tenant and is in spn: format

When the Windows Azure Active Directory developer preview issues a token for an application, the audience URI in the token includes the identifier of the application and the identifier of the tenant instead of just the identifier of the application. For a Windows Identity Foundation-based application to handle this tenant-varying audience URI, extension code to WIF is required, and has been supplied in the web SSO samples. Also, the audience URI is in spn: format instead of being the more familiar URL of the application. In a future release, Windows Azure Active Directory will support the audience URI being the URL of the application and not have a tenant-varying component.

##### SAML Token has no AuthenticationStatement

During this Preview release, our current implementation does not return an AuthenticationStatement. Authentication statements assert to the service provider that the principal did indeed authenticate with the identity provider at a particular time using a particular method of authentication.

## About The Code

Code hosted on GitHub under Apache 2.0 license

We encourage you to download and use this sample code in your own Visual Studio setup. This demo application will be updated with additional features and documentation as the platform evolves. Community participation, including github pull requests and documentation updates are encouraged.

In order to build this demo application yourself, you will need to download:

- [Windows Azure SDK][asdk]
- [MVC3 Frameowrk from Web Components installation][MVC3]
- [Windows Identity Foundation Runtime][WIFR]
- [Windows Identity Foundation SDK][WIFSDK]
- [WCF Data Services 5.0 for OData V3][WCFD]
- [Microsoft .Net 4 or higher][NET4]

[asdk]: http://www.windowsazure.com/en-us/develop/downloads/ "Windows Azure SDK"
[mvC3]:http://www.asp.net/mvc/mvc3
[wifr]:http://www.microsoft.com/en-us/download/details.aspx?id=17331
[wifsdk]:http://www.microsoft.com/en-us/download/details.aspx?id=4451
[wcfd]:http://www.microsoft.com/en-us/download/details.aspx?id=29306
[net4]:http://www.microsoft.com/en-us/download/details.aspx?id=17851
