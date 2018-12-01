# e-Mpiya Foundation
e-Mpiya Online and Mobile Payment System (OMPS) is a [One Ziko](https://oneziko.com/) payment service that leverages on existing payment options to bridge financial inclusion in Zambia. This repository is the foundation on which this payment system based. Feel free to contribute, use and improve upon it.

## Table Of Contents (TOC)
1.	Setup SoapUI Test Environment
	1.	Identify API
	2.	Get WSDL
	3.	Import WSDL into SOAPUI
	4.	Test Services
2.	Develop Web Client
	1.	Basic Web Form
	2.	Using Laravel Blade
	3.	Test With SoapUI
	
## Some Things To Note
With the TOC outlined above, we can start by aligning with expectations. Ideally, it would be good to integrate with all three (3) mobile network operators (MNOs) in Zambia, i.e. Airtel, MTN and ZAMTEL, and also other mobile financial services such as Zoona, Kazang, SpeedPay, etc. But as it stands, we are restricted by non-availability of public Application Programming Interfaces (API's) for developers to work with from the mentioned services. Hopefully, by the time you are reading this, that would have changed.

So, for now;
* We are going to work with [MTN API](https://developer.mtn.com/community/portal/site.action?s=devsite&c=Home), since MTN has a developer portal with a bunch of useful resources. As and when other third-parties open up, we can integrate with them.
* We are not going to be working with MTN sandbox or test environment. I will take it we are starting from scratch and hence we will first need to establish a basis with which to argue viability of the project. Therefore, we will use [SoapUI](https://www.soapui.org/downloads/latest-release.html) to create a local test environment with which to develop.
* We will be using the [MobileMoney SOAP API specification](https://developer.mtn.com/community/portal/site.action?s=devsite&c=detailsResource&resourceId=613&categoryId=DEV1000002&search=DEV1000002&resourceName=MobileMoney%20API%20specification%20v11&h=firresource&currentPage=1&osIds=DEV2000001,DEV2000002,DEV2000003,DEV2000004,DEV2000005&flag=fromRight&fromApiResource=yes) and as at now, 1st December, 2018, the latest WSDL files we are using are here:  [MobileMoney-ECW_WSDL_6_1](https://developer.mtn.com/community/portal/site.action?s=devsite&c=detailsResource&lang=en&t=web&resourceId=421&resourceName=%3Cspan%20style=%22color:#1483BB;background:#FFFFFF;%22%3EMobileMoney%3C/span%3E-ECW_WSDL_6_1&categoryId=&h=resourceSearch&searchName=&search=&currentPage=1)
* We will have to come up with a way of requesting and responding in SOAP format, after setting up a test environment. There are so many ways you can do this, actually, MTN developer portal has guides in three (3) programming languages: C#, JAVA and PHP, with Apache Tomcat. We will be using PHP with Laravel framework and the method we will be using is not documented on the MTN portal, this is what I have found to be a convenient way to achieve communication with server without third-party libraries. But all in all, the principles are the same, using GET and POST.
* Lastly, if you're at all lost and need some background, I recommend that you look at this presentation that we had at Bongo Hive a while back: [Code and notes for MTN API session at Bongo Hive](https://github.com/Chizzoz/MTN-API-BongoHive-Session).
* And one last thing, I don't think we will include any database integration with this repository, you can decide how and what to use to store data. We will be satisfied with successfully requesting and responding to the API as required.

## Filling In The Blanks
1.	**Setup SoapUI Test Environment**
	1.	**Identify API:**
	
		It seems I was rushing things, this was already mentioned adove. Download API: [MobileMoney SOAP API specification](https://developer.mtn.com/community/portal/site.action?s=devsite&c=detailsResource&resourceId=613&categoryId=DEV1000002&search=DEV1000002&resourceName=MobileMoney%20API%20specification%20v11&h=firresource&currentPage=1&osIds=DEV2000001,DEV2000002,DEV2000003,DEV2000004,DEV2000005&flag=fromRight&fromApiResource=yes)
	2.	**Get WSDL:**
	
		Then download and extract WSDL files to help develop web services: [MobileMoney-ECW_WSDL_6_1](https://developer.mtn.com/community/portal/site.action?s=devsite&c=detailsResource&lang=en&t=web&resourceId=421&resourceName=%3Cspan%20style=%22color:#1483BB;background:#FFFFFF;%22%3EMobileMoney%3C/span%3E-ECW_WSDL_6_1&categoryId=&h=resourceSearch&searchName=&search=&currentPage=1)
		
	3.	**Import WSDL into SOAPUI:**
	
		TODO
	4.	**Test Services:**
	
		TODO
2.	**Develop Web Client**
	1.	**Install and Setup Web Client:**

		The following are the server requirements:
		* PHP >= 7.1.3
		* OpenSSL PHP Extension
		* PDO PHP Extension
		* Mbstring PHP Extension
		* Tokenizer PHP Extension
		* XML PHP Extension
		* Ctype PHP Extension
		* JSON PHP Extension
		* BCMath PHP Extension
		
		Install Laravel: ``` composer create-project --prefer-dist laravel/laravel e-mpiya-foundation ```
		
		Now Laravel ships with Bootstrap frontend preset, but we will be using [Zurb Foundation](https://foundation.zurb.com/). By the way, just to make it clear, this repository is *e-mpiya-foundation*, but that foundation does not refer to Foundation frontend scripting, it's just a coincindence, I meant foundation as in basis or groundwork for the payment system.
		
		Anyhow, to achieve this, we will be using [Zurb Foundation Frontend Preset For Laravel Framework 5.5 and Up](https://github.com/laravel-frontend-presets/zurb-foundation)
		
		Install: ``` composer require laravel-frontend-presets/zurb-foundation ```
		
		Set Foundation preset: ``` php artisan preset foundation-auth ```
		
		Run: ``` npm install ```
		
		Then run: ``` npm run dev ``` OR ``` npm run development ```
		
		We'll stop here since we are not doing any database integration.
		
		Now, I think we will only concern ourselves with basically four (4) folders:
		* Views: ``` e-mpiya-foundation\resources\views\ ```
		* Routes: ``` e-mpiya-foundation\routes\ ```
		* Controllers: ``` e-mpiya-foundation\app\Http\Controllers\ ```
		* We might also have to frequent the ``` e-mpiya-foundation\public ``` folder to handle CSS and JS dependency
		
	2.	**Basic Web Form:**
	
		TODO
	3.	**Using Laravel Blade:**
	
		TODO
	4.	**Test With SoapUI:**
	
		TODO