# `What Is Keycloak?`

> It is a tool for “Identity and Access Management”, as written on their project page on GitHub. Additionally, Keycloak is an open-source tool currently licensed with Apache License 2.0. It is also an upstream project for Red Hat SSO, so if you are looking for something more enterprise-centered, you can check it. 


The full list of supported platforms depends on which protocol you decide to use, currently Keycloak supports three different protocols, and can be viewed in documentation. Keycloak’s initial release took place in September 2014; the current version is 15.0.2 (2021-10-09). It is developed and maintained by people from Red Hat. They are open to new contributors if anyone is interested.

![keycloak-overview](https://github.com/paulveillard/cybersecurity-keycloak/blob/main/img/Keycloak-overview.png)

## `Table of Contents`
- [Keycloak Features](#keycloak-features)
- [Distributions of Keycloak](#distribution-of-keycloak)
- [Keycloak Integrations](#keycloak-integrations)
- [Why You Should Know Keycloak](#why-you-should-know-keycloak)
- [Summing up](#summing-up)
- [FAQ](#faq)

## `Keycloak Features`

After the brief introduction from the previous paragraph, I think it is time to tell you more about what Keycloak can do.

    Multiple Protocols Support
    As for now Keycloak supports three different protocols, namely - OpenID Connect, OAuth 2.0 and SAML 2.0.
    
    SSO
    Keycloak has full support for Single Sign-On and Single Sign-Out.
    
    
    Admin Console
    Keycloak offers web-based GUI where you can “click out” all configurations required by your instance to work as you desire.
    
    
    User Identity and Accesses
    Keycloak can be used as a standalone user identity and access manager by allowing us to create users database with custom roles and groups. This information can be further used to authenticate users within our application and secure parts of it based on pre-defined roles.
    
    
    External Identity Source Sync
    In case when your client currently has some type of user database, Keycloak allows us to synchronize with such database. By default, it supports LDAP and Active Directory but you can create custom extensions for any user database using Keycloak User storage API. Keep in mind that such a solution may not have all data necessary for Keycloak to be fully functional, so remember to check if your desired functionality works.
    
    
    Identity Brokering
    Keycloak can also work as a proxy between your users and some external identity provider or providers. Their list can be edited from Keycloak Admin Panel.
    
    
    Social Identity Providers
    Additionally, Keycloak allows us to use Social Identity Providers. It has built-in support Google, Twitter, Facebook, Stack Overflow but, in the end, you have to configure all of them manually from admin panel. The full list of supported social identity providers and their configuration manual can be found in Keycloak documentation.
    
    
    Pages Customization
    Keycloak lets you customize all pages displayed by it to your users. Those pages are in .ftl format so you can use classic HTML  markups and CSS styles to make the page fit your  application style and your company brand. You can even put custom JS scripts as part of pages customization so possibilities are limitless.

These are all of Keycloak features which I wanted to describe today. Of course, this tool offers even more possibilities, which are described in a much more detailed way in the documentation. 


## `Distributions of Keycloak`

Currently, Keycloak has three major distributions.

    Server
    Standalone application is downloadable from Keycloak page in form of a tar or zip archive with all scripts, docs, and assets needed to work normally. As for now, there are two main versions of this distribution: one is powered by WildFly server while the other is powered by Quarkus. It is now in preview stage so some unexpected error may occur.
    
    
    Docker Image
    Distribution appropriate for Docker, Podman, Kubernetes, and OpenShift. There are two official docker images for Keycloak: one is held in Quay Container Registry - quay.io/keycloak/keycloak, the second one is held in Docker Hub - jboss/keycloak. You can download both of them with a simple docker pull command.
    
    
    Operator
    Distribution for Kubernetes and OpenShift based on Operator SDK.

As you can see, everybody can find an appropriate distribution. If you use Docker or Kubernetes you have Keycloak image and operator. On the other hand, if you prefer a more conventional deployment type you will also find a distribution for you. Even then Keycloak Docker image can be extremely useful for development and testing. 

You can set up your test Keycloak server then do changes and test them. After tests you can restart your Docker image and all changes made to your Keycloak will be reverted and you will get a clear environment for further tests. All three distributions can be downloaded from here.

## Keycloak Integrations

So now you know basics of Keycloak and its features. The last remaining question is - how to integrate it into your app? 

Here I will speak mostly from the perspective of Java eco-system but I will mention also some other languages and frameworks. In Java currently the most popular frameworks like Spring Boot, Quarkus and Micronaut have some sort of adapters that make integrating with Keycloak really easy.

In case of Spring Boot, it is spring-boot-keycloak-starter while in case of Quarkus it is quarks-keycloak-authorization.

On the other hand, in Python package python-keycloak seems pretty useful. 

For Scala-based application library, keycloak4s also sounds good. 

For C# based application Keycloak.Net looks like a handy lib. 

All libraries are open source, developed and maintained by the community built around Keycloak. I will put respective links in the end of the article.

In the case of Spring Boot and Quarkus, thanks to the framework provided abstractions, the whole integration requires just a few lines of code and filling some configuration properties. In other cases, libraries only provide clients for Keycloak API so integration could be more complex.


## Why You Should Know Keycloak

> First of all, it is free. You may think that it is funny but in fact, most tools with such features like AuthO or Okta are paid. 

Secondly, it supports three different authentication protocols which give you the possibility to cover many applications with different security demands with a single tool. 

Additionally, you can choose an authentication protocol basing on what you need or what you think will be better for your application and you are not limited by the tool you are using. Keycloak is also an upstream project for Red Hat SSO product so you can be sure that it is a well written and well designed system.

Moreover, it has big community support which guarantees that there are a lot of examples of how to do something and that you can count on others to help you with your problems. Keycloak can be very useful when your client has some existing user database like LDAP or Active Directory because it has a built-in mechanism for synchronization with such identity providers. 

Additionally, Keycloak supports social identity providers like Google or Facebook straight out of the box so if you want to use Social Login, Keycloak may be very useful for you and your team. 

Furthermore, it provides web-based GUI which makes any configurations changes easier. In the end, thanks to Keycloak SSO support you can facilitate your users’ access to multiple services run by your company.

## When It May Not Be the Best Choice

I said why you should use Keycloak so, to stay objective, I will say something about when it may not be the best choice for you.

    Single application with just one client in Keycloak realm – lose all benefits of SSO

    No integration with AD or any other user data provider

    No Social Login

    Pure user database — Keycloak can be used this way but so can a database with specific tables, and it can be much easier to configure if you already have one

    Some kind of enterprise-level guarantees — Keycloak is still an open-source project so you do not have any guarantee provided by its producer about its working or road map and things likes customer support are taken care of by Stack Overflow and surely with no hard deadlines for response time

Keep in mind that meeting any or even all of these conditions by your application does not straight away indicate that you should not be using Keycloak. It only means that it may be profitable for you to reconsider pros and cons of securing your application with Keycloak. Perhaps there is a less complex tool or solution that can be used.

## Summing up

I presented some basic information about what Keycloak is, which features it provides, and added few words about its different distributions. I concluded with a short explanation when it may be the better choice than others tools and when it may not. I hope that my article gave you some more general knowledge about Keycloak itself, what it offers and when it may help you. The final decision about diving deeper into Keycloak I leave to you.



## [FAQ](https://dzone.com/articles/what-is-keycloak-and-when-it-may-help-you)

    What is Keycloak?
    Keycloak is a tool for Identity and Access Management.
    
    
    Is Keycloak free?
    Yes, as for now Keycloak is open-source and has Apache License 2.0.
    
    
    Which security protocols are supported by Keycloak?
    As for now Keycloak supports OpenID Connect, OAuth 2.0 and SAML 2.0.
    
    
    Does Keycloak support SSO?
    Yes, Keycloak support both Single Sign-On and Single Sign-Out.
    
    
    What are current Keycloak distributions?
    As for now, Keycloak has 3 different distributions: Server, Docker image and Operator.
    
    
    How can I integrate Keycloak?
    Keycloak provides API and client library which you can use in your application. Additionally, there are several implementations of this library in many different languages.
    
    
    Is there a tool like Keycloak with enterprise support?
    Keycloak is an upstream project for Red-hat SSO so I recommend checking it.

