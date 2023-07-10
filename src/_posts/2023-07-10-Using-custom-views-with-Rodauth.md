---
layout: post
title:  "Replacing Rodauth's authentication templates"
date:   2023-07-10
blurb: "Rodauth is a great solution for authentication in a Ruby app. Let's change out the default views with custom styled views."
image_url: https://rodauth.jeremyevans.net/images/rodauth.svg
---

I'm building a workout app called [https://tectonicplates.app](https://tectonicplates.app). I wanted to add authentication to the app, so I incorporated Rodauth, a gem from the creator of Roda. 

&nbsp;


It comes with default templates for login, logout, create an account, etc. But those views use Bootstrap tags, and I'm using Tailwind in my project instead. So I wanted to replace the default templates with custom templates.

&nbsp;


I ran the `rodauth.login_view` method to grab the HTML for the default view. I coped the HTML generated from that method, and decoded it. I copied and pasted that HTML into a login.erb file in the /views/ directory. Rodauth immediately picked it up and used it as the login page.

&nbsp;

I tried logging in using my new page, but got an error.

&nbsp;

```
Roda::RodaPlugins::RouteCsrf::InvalidToken at /login"
```

&nbsp;


![CSRF Error with Rodauth](/images/rodauth_error.png "CSRF Error with Rodauth")

&nbsp;

This error is coming from this line:

&nbsp;


```
<input type="hidden" name="_csrf" 
value="RCc5iYNpPhXN" />
```

&nbsp;


My hunch is that I need to replace the value of the CSRF token with one that is generated on the fly. I'm guessing there is some sort of method that Rodauth uses to generate these tokens. 

&nbsp;


I couldn't find anything in the documentation about how to generate a csrf token. I saw info about switching to Rack's CSRF features, but not about how to generate a token. 
