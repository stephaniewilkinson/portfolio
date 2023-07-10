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

&nbsp;



My first try was replacing the token with csrf_token, but that didn't work.

&nbsp;


```
<input type="hidden" name="_csrf" value="<%= csrf_token %>" />
```

&nbsp;



```
Roda::RodaPlugins::RouteCsrf::InvalidToken at /login
decoded token is not valid for request method and path (Roda::RodaPlugins::RouteCsrf::InvalidToken)
```

&nbsp;

My second try was replacing the entire input line with 
<%= csrf_tag %> since it generates the html.

&nbsp;


But then I got the same error as the one I started with: 

&nbsp;

```
Roda::RodaPlugins::RouteCsrf::InvalidToken at /login
decoded token is not valid for request method and path (Roda::RodaPlugins::RouteCsrf::InvalidToken)
```

&nbsp;

None of the other options looked helpful, after looking through the output of each one.

![CSRF methods](/images/csrf_methods.png "CSRF methods")

&nbsp;

My third idea was to see if there was a Rodauth sample app somewhere, and I could copy the code to generate the token from there.

&nbsp;


[The rodauth-rails gem has an example app, but it didn't create any tokens on the page.](https://github.com/janko/rodauth-demo-rails/blob/master/app/views/rodauth/login.html.erb)
