# Introduction

This is a community initiative by members of the last.fm Discord to create better documentation for the last.fm API. Anyone is welcome to join and help create better documentation.

## What makes this better then the official documentation?

There are multiple reasons we're doing this:

- The official docs often have outdated examples, and they're all in XML
- Examples with parameters and showing what objects to expect are easier to work with
- The API often has weird behaviour that we feel should be documented so developers don't have to figure that out themselves
- Error responses are often inconsistent and don't match the docs. It would save developers time if they are well documented
- Documentation should be open source so anyone can fix errors if they find them

## Sounds great! How can I contribute?

You can check out the docs [here](https://github.com/lastfm-docs/api-docs/tree/master/docs). 

It's all in markdown, so easy to work with. Please follow the other pages in styling and objects.

We use MkDocs with some extensions for extra markdown types. Some of the extensions are: [Tabbed](https://facelessuser.github.io/pymdown-extensions/extensions/tabbed/) and [Details (collapsible objects)](https://facelessuser.github.io/pymdown-extensions/extensions/details/)

## Last.fm's API Terms of Service

Please carefully read [this](https://www.last.fm/api/tos) agreement  before using Last.fm's webservices, as it affects your legal rights and obligations. This agreement governs the way that you are permitted to access Last.fm data via the API. By accessing the API, You agree to accept and abide by the terms set out in the agreement in respect of your access to and use of the Last.fm data.

!!! warning "Note"
	- Please use an identifiable User-Agent header on all requests. This helps Last.fm's logging and reduces the risk of you getting banned.
	- Be reasonable in your usage of the API and ensure you don't make an excessive number of calls as that can impact the reliability of the service to you and other users. Last.fm encourage best practice implementation, for example, if you're making a web application, try not to hit the API on page load. Your account may be suspended if your application is continuously making several calls per second or if you’re making excessive calls. See our [API Terms of Service](https://www.last.fm/api/tos) for more information on limits.
	- If you are planning to use Last.fm's API for commercial purposes, please contact them via email at [partners@last.fm](mailto:partners@last.fm).
	- Last.fm assume that you are using an RFC 3986-compliant HTTP client to access the web services. In particular, pay attention to your url encoding. This will not be an issue for 99% of developers.