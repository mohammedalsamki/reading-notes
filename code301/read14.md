What is OAuth? How the open authorization framework works
OAuth allows websites and services to share assets among users. It is widely accepted, but be aware of its vulnerabilities.
     
By Roger A. Grimes and Josh Fruhlinger
CSO | SEP 20, 2019 3:00 AM PDT

Admission tickets in an digital network / access / admittance / authorization / authentication
WildPixel / Your Photo / Getty Images
WHITE PAPERS
	
Boost competitiveness and reduce risk with secure DevOps

	
Webinar on Accelerating Analytics with Amazon QuickSight

	
Gartner Magic Quadrant for WAN Edge Infrastructure Report

SEE ALL WHITE PAPERS
Since the beginning of distributed personal computer networks, one of the toughest computer security nuts to crack has been to provide a seamless, single sign-on (SSO) access experience among multiple computers, each of which require unrelated logon accounts to access their services and content. Although still not fully realized across the entire internet, myriad, completely unrelated websites can now be accessed using a single physical sign-on. You can use your password, phone, digital certificate, biometric identity, two-factor authentication (2FA) or multi-factor authentication (MFA) SSO solution to log onto one place, and not have to put in another access credential all day to access a bunch of others. We have OAuth to thank for much of it.

OAuth definition
OAuth is an open-standard authorization protocol or framework that describes how unrelated servers and services can safely allow authenticated access to their assets without actually sharing the initial, related, single logon credential. In authentication parlance, this is known as secure, third-party, user-agent, delegated authorization.

[ Read reviews of the best tools for single sign-on. | Sign up for CSO newsletters. ]

OAuth history
Created and strongly supported from the start by Twitter, Google and other companies, OAuth was released as an open standard in 2010 as RFC 5849, and quickly became widely adopted. Over the next two years, it underwent substantial revision, and version 2.0 of OAuth, was released in 2012 as RFC 6749. Even though version 2.0 was widely criticized for multiple reasons covered below, it gained even more popularity. Today, you can add Amazon, Facebook, Instagram, LinkedIn, Microsoft, Netflix, Paypal and a list of other internet who’s-whos as adopters.

OAuth examples
The simplest example of OAuth is when you go to log onto a website and it offers one or more opportunities to log on using another website’s/service’s logon. You then click on the button linked to the other website, the other website authenticates you, and the website you were originally connecting to logs you on itself afterward using permission gained from the second website.

Another common example OAuth scenario could be a user sending cloud-stored files to another user via email, when the cloud storage and email systems are otherwise unrelated other than supporting the OAuth framework (e.g., Google Gmail and Microsoft OneDrive). When the end-user attaches the files to their email and browses to select the files to attach, OAuth could be used behind the scenes to allow the email system to seamlessly authenticate and browse to the protected files without requiring a second logon to the file storage system. Another example, one given in the OAuth 2.0 RFC, is an end-user using a third-party printing service to print picture files stored on an unrelated web server.

In all cases, two or more services are being used for one transaction by the end-user, and every end-user would appreciate not being asked to log in a second time for what they feel is a single transaction. For OAuth to work, the end-user’s client software (e.g., a browser), the services involved and authentication provider must support the right version of OAuth (1.0 versus 2.0).

OAuth explained
When trying to understand OAuth, it can be helpful to remember that OAuth scenarios almost always represent two unrelated sites or services trying to accomplish something on behalf of users or their software. All three have to work together involving multiple approvals for the completed transaction to get authorized.

RECOMMENDED WHITEPAPERS
	
Boost competitiveness and reduce risk with secure DevOps

	
Webinar on Accelerating Analytics with Amazon QuickSight

	
Gartner Magic Quadrant for WAN Edge Infrastructure Report

It is also helpful to remember that OAuth is about authorization in particular and not directly about authentication. Authentication is the process of a user/subject proving its ownership of a presented identity, by providing a password or some other uniquely owned or presented factor. Authorization is the process of letting a subject access resources after a successful authentication, oftentimes somewhere else. Many people think that OAuth stands for open authentication, but it’s more helpful to understand it by thinking about it as open AUTHorization.

An early implementer describes OAuth as similar to a car’s valet key, which can be used to allow a valet to temporarily drive and park a car, but it doesn’t allow the holder full, unlimited access like a regular key. Instead the car can only be driven a few miles, can’t access the trunk or locked glove box, and can have many other limitations. OAuth essentially allows the user, via an authentication provider that they have previously successfully authenticated with, to give another website/service a limited access authentication token for authorization to additional resources.

Additionally, OAuth 2.0 is a framework, not a protocol (like version 1.0). It would be like all the car manufacturers agreeing on how valets would automatically request, receive and use valet keys, and how those valet keys would generally look. What the valet keys could do as compared to the full function keys would be up to each car manufacturer. Just like in real life, valets and car owners don’t need to care about how it all works. They just want it all to work seamlessly as possible when they hand off the key.

How OAuth works
Let’s assume a user has already signed into one website or service (OAuth only works using HTTPS). The user then initiates a feature/transaction that needs to access another unrelated site or service. The following happens (greatly simplified):

The first website connects to the second website on behalf of the user, using OAuth, providing the user’s verified identity.
The second site generates a one-time token and a one-time secret unique to the transaction and parties involved.
The first site gives this token and secret to the initiating user’s client software.
The client’s software presents the request token and secret to their authorization provider (which may or may not be the second site).
If not already authenticated to the authorization provider, the client may be asked to authenticate. After authentication, the client is asked to approve the authorization transaction to the second website.
The user approves (or their software silently approves) a particular transaction type at the first website.
The user is given an approved access token (notice it’s no longer a request token).
The user gives the approved access token to the first website.
The first website gives the access token to the second website as proof of authentication on behalf of the user.
The second website lets the first website access their site on behalf of the user.
The user sees a successfully completed transaction occurring.
OAuth is not the first authentication/authorization system to work this way on behalf of the end-user. In fact, many authentication systems, notably Kerberos, work similarly. What is special about OAuth is its ability to work across the web and its wide adoption. It succeeded with adoption rates where previous attempts failed (for various reasons).
Although not as simple as it could be, web coders seem to readily understand the involved transactions. Making a website OAuth-compatible can be done in a few hours to a day (much faster if you’ve done it before). For a little bit of extra effort, authenticated website access can be extended to literally hundreds of millions of additional users. There’s no need for a website to contain its own authentication system with the ability to scale to gigantic proportions. You can find an example of an individual HTTP transaction packet here.

OAuth vs. OpenID
There are a couple of other security technologies that you might hear about in the same context as OAuth, and one of them is OpenID. At a base level, the distinction between the two is simple to grasp. Remember when we said up above that the auth in OAuth stood for authorization, not authentication? Well, OpenID is about authentication: as a commenter on StackOverflow pithily put it: "OpenID is for humans logging into machines, OAuth is for machines logging into machines on behalf of humans."

OpenID began life in 2005 as a means for logging into the then-popular LiveJournal blogging site but quickly spread to other sites. The idea, in the early days of Web 2.0, was that rather than having multiple logins for multiple websites, OpenID would serve as a single sign-in, vouching for the identities of users. But in practice OpenID was difficult to implement on the developer side, and never really became that appealing to users, especially as there was competition in that space. By 2011, OpenID had become an also-ran, and, Wired declared that "The main reason no one uses OpenID is because Facebook Connect does the same thing and does it better. Everyone knows what Facebook is and it's much easier to understand that Facebook is handling your identity than some vague, unrecognized thing called OpenID." (Facebook Connect turned out to not be a world-beater either, but at least people knew what Facebook was.)

That's not quite the end of the story, though. In 2014, OpenID Connect was released, which reinvented OpenID as an authentication layer for OAuth. In this space, OpenID has found a niche, and the two technologies now complement each other in many implementations.

OAuth vs. SAML
The Security Assertion Markup Language, or SAML, is another technology you'll hear talked about in the same breath as OAuth. Strictly speaking, the name SAML refers to an XML variant language, but the term can also cover various protocol messages and profiles that make up part of the open SAML standard. SAML describes a framework that allows one computer to perform both authentication and authorization on behalf of one or more other computers, unlike OAuth, which requires an additional layer like OpenID Connect to perform authentication. SAML can provide single sign-on functionality on its own.

SAML is older than OAuth, and indeed one of the driving factors behind OAuth's creation was that XML protocols like SAML began falling out of vogue; OAuth uses the lighter weight JSON for encoding data, and thus has better support for mobile devices. In practice, SAML is more often used for enterprise applications — Salesforce uses it for single sign-on, for instance — whereas OAuth is more often in use on the open internet.

OAuth2
There are no perfect universal internet-wide authentication standards. OAuth is particularly maligned because of the drastic changes between versions 1.0 and 2.0. In many ways, OAuth2 is less secure, more complex and less prescriptive than version 1.0. Version 2.0 creators focused on making OAuth more interoperable and flexible between sites and devices. They also introduced the concept of token expiration, which did not exist in version 1.0. Regardless of the intent, many of the original founders and supporters threw up their hands and did not support version 2.0.

The changes are so significant that version 2.0 is not compatible with version 1.0, and even different implementations of version 2.0 may not work seamlessly with each other. However, nothing prevents a website from supporting both 1.0 and 2.0, although the 2.0 creators released it with the intent of all websites completely replacing version 1.0.

One of the biggest criticisms of OAuth 2.0 is that the standard intentionally does not directly define or support encryption, signature, client verification or channel binding (tying a particular session or transaction to a particular client and server). Instead, OAuth expects implementers to use an outside protection protocol like Transport Layer Security (TLS), to provide those features.

# Is OAuth safe?
TLS can provide all those protections, but it’s up to the implementers, on all sides, to require it to be used. Coders and users should look to ensure that OAuth is running inside of TLS protection. Developers can implement code to enforce TLS use and users should be aware that TLS is being used whenever they are begin asked to input authentication credentials (just like they should anytime they are entering in credentials).

Because of the lack of inherent security binding, it’s possible for a rogue website to phish a user’s legitimate credentials during the part of the process where the user is being required to authenticate themselves to the authorization provider. For example, a user is using the first service and chooses a feature that forces an OAuth transaction to a second service. It’s possible for the first website to fake the second website, where user authentication is often taking place. The rogue website can then collect the user’s authentication credentials and react as if the OAuth transaction had successfully taken place.

This is not just a theoretical threat. In the second quarter of 2017, a million Google accounts were successfully phished. The defense is for users to ensure they are entering their credentials in the legitimate second website’s domain if prompted for credentials, and to avoid nebulous first websites. There is no perfectly safe, universally accepted, SSO that works on all websites, but with OAuth, we’re getting closer.

More on single sign on and identity management:

What is identity management? Its definition, uses and solutions 
The best identity management advice right now
What is SAML, what is it used for and how does it work?
Next read this
21 best free security tools
Top cyber security certifications: Who they're for, what they cost, and which you need
10 security tools all remote employees should have
7 tenets of zero trust explained
Tabletop exercises: Six sample scenarios
How to rob a bank: A social engineering walkthrough
5 biggest healthcare security threats for 2021
AWS, Google Cloud, and Azure: How their security features compare
Securing CI/CD pipelines: 6 best practices
12 tips for effectively presenting cybersecurity to the board
The state of security hiring: Jobs, skills, and salaries
Related: Authentication Security Internet
Copyright © 2019 IDG Communications, Inc.

 How to choose a SIEM solution: 11 key features and considerations
CSO OnlineCSO provides news, analysis and research on security and risk managementFOLLOW US
ABOUT USCONTACTREPRINTSPRIVACY POLICYCOOKIE POLICYMEMBER PREFERENCESADVERTISINGIDG CAREERSAD CHOICESE-COMMERCE LINKSCALIFORNIA: DO NOT SELL MY PERSONAL INFO
IDG Communications
Copyright © 2021 IDG Communications, Inc.

Explore the IDG Networkdescend
