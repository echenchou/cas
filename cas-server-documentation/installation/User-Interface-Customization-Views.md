---
layout: default
title: CAS - User Interface Customization
---

# Views
The views are found at `src/main/resources/templates`.

## Warning Before Accessing Application
CAS has the ability to warn the user before being redirected to the service. This allows users to be made aware whenever an application uses CAS to log them in.
(If they don't elect the warning, they may not see any CAS screen when accessing an application that successfully relies upon an existing CAS single sign-on session.)
Some CAS adopters remove the 'warn' checkbox in the CAS login view and don't offer this interstitial advisement that single sign-on is happening.

```html
...
<input id="warn"
       name="warn"
       value="true"
       tabindex="3"
       th:accesskey="#{screen.welcome.label.warn.accesskey}"
       type="checkbox" />
<label for="warn" th:utext="#{screen.welcome.label.warn}"/>
...
```

## "I am at a public workstation" authentication

CAS has the ability to allow the user to opt-out of SSO, by indicating on the login page that the authentication
is happening at a public workstation. By electing to do so, CAS will not honor the subsequent SSO session
and will not generate the TGC that is designed to do so.

```html
...
<input id="publicWorkstation"
       name="publicWorkstation"
       value="false" tabindex="4"
       type="checkbox" />
<label for="publicWorkstation" th:utext="#{screen.welcome.label.publicstation}"/>
...
```
