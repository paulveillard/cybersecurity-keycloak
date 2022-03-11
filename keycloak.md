# What Is Keycloak?

It is a tool for “Identity and Access Management”, as written on their project page on GitHub. Additionally, Keycloak is an open-source tool currently licensed with Apache License 2.0. It is also an upstream project for Red Hat SSO, so if you are looking for something more enterprise-centered, you can check it. 


The full list of supported platforms depends on which protocol you decide to use, currently Keycloak supports three different protocols, and can be viewed in documentation. Keycloak’s initial release took place in September 2014; the current version is 15.0.2 (2021-10-09). It is developed and maintained by people from Red Hat. They are open to new contributors if anyone is interested.

# Keycloak Features

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


# Distributions of Keycloak

Currently, Keycloak has three major distributions.

    Server
    Standalone application is downloadable from Keycloak page in form of a tar or zip archive with all scripts, docs, and assets needed to work normally. As for now, there are two main versions of this distribution: one is powered by WildFly server while the other is powered by Quarkus. It is now in preview stage so some unexpected error may occur.
    
    
    Docker Image
    Distribution appropriate for Docker, Podman, Kubernetes, and OpenShift. There are two official docker images for Keycloak: one is held in Quay Container Registry - quay.io/keycloak/keycloak, the second one is held in Docker Hub - jboss/keycloak. You can download both of them with a simple docker pull command.
    
    
    Operator
    Distribution for Kubernetes and OpenShift based on Operator SDK.

As you can see, everybody can find an appropriate distribution. If you use Docker or Kubernetes you have Keycloak image and operator. On the other hand, if you prefer a more conventional deployment type you will also find a distribution for you. Even then Keycloak Docker image can be extremely useful for development and testing. 

You can set up your test Keycloak server then do changes and test them. After tests you can restart your Docker image and all changes made to your Keycloak will be reverted and you will get a clear environment for further tests. All three distributions can be downloaded from here.