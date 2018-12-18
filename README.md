# Integrated_Okta_SSO_Using_SAML
# Description:


Company(Hashworks IT Services Private Limited)_Internship_Project.

Download all files and put it in one folder. After that open that folder on Visaul Studio Code editor and install Node modules with help of "npm install" command. Then, comiple that project using "ng serve" command. Finally, open it on your favorite browser using http://localhost:4200 url.

Technology Used: HTML/HTML5, CSS/CSS3, Angular7, Okta SSO, SAML Server.

Duration: Nov, 2018 to Dec, 2018.

# Procedure:

First thing you have to do create an account on https://developer.okta.com . Now create one identity management application(SSO) on okta application section, while creating this have ensure couple of things like application name, base url, Login redirect url (http://localhost:4200/callback), Logout redirect url (http://localhost:4200/login) and after creating it you will get that own "Client ID". 

Now, open Visual Studio Code and create your angular application using "ng new 'project name'" command. then, we need to install signin-widget using "npm install @okta/okta-signin-widget --save" command and install okta dependency using "npm install @okta/okta-angular --save" command.

After that, Some routes require authentication in order to render. Defining these protected routes is easy with the OktaAuthGuard from @okta/okta-angular. This route will only be visible to users with a valid accessToken or idToken. When a user attempts to access a route that is protected by OktaAuthGuard, it first checks to see if the user has been authenticated. If is Authenticated() returns false, start the login flow. Inside the html component create Home, Login, Logout button with onclick function.

/login
This route hosts the Sign-In Widget and redirects if the user is already logged in. Create a new component "src/app/login.component.ts" and on that file have to put base url.

The OktaAuthModule handles different authentication flows for your application, so it requires your OpenID Connect configuration. By default okta/okta-angular redirects to the Okta Sign-In Page when the user is not authenticated. We override this behavior by passing an onAuthRequired function to the OktaAuthGuard. 

Update src/app/app.module.ts to include your project components and routes. Here ensure couple of things like  issuer: 
"https://{yourOktaDomain}/oauth2/default", redirectUrl: "http://localhost:4200/implicit/callback", clientId: "{clientId}"
 
 Finally, start the application using "ng serve" command.


