---
layout: post
title:  "School Location API"
date:   2018-01-19
category: Nonprofit
image_url: './images/school_location_api.png'
blurb: "A Ruby/Roda API built to interface between a legacy MS SQL Server database and an Elixir API"
tags:
- ruby
- roda
- mssql
- api
---

This was a Ruby/Roda app I built and deployed on a Digital Ocean droplet. Its purpose was to extract data from an antiquated Microsoft Sequel Server database from 2009 and serve it up to an Elixir app.

&nbsp;

This was an extrememly challenging app because I had to use TDS as a data connection protocol instead of ODBC, and employ a Ruby TDS driver. Also the host had ACL which meant I couldn't use a server which dynamically assigned IPs, and instead had to spin up an Ubuntu box to make requests.
