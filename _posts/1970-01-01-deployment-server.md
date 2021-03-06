---
layout: post
title: Deployment and Server
order: 230
---

TODO

* [Capistrano](http://capistranorb.com/)

Alternative solutions like Mina do not have any major advantages at the moment.
Or a custom Deploy workflow for big projects with tools like Ansible

### VPS, Dedicated server

* [DigitalOcean](https://m.do.co/c/20534050b97f) (my ref link ;) you receive $10 credit after registration)
* [Amazon Web Services]()
* [Namecheap, domains registrator](https://www.namecheap.com/?aff=62428) (my ref link ;) )

### PaaS

* [Heroku](https://www.heroku.com/)

### CI 

* [Jenkins](https://jenkins.io/)
* [Travis CI](https://travis-ci.org/)
* [CircleCI](https://circleci.com/)

### DevOps

TODO

* Ansible
* Chef
* Puppet
* Docker

### Local development

TODO

* Vagrant
* Docker

### Local tunnels. Exposing dev env in the Internet

* Ngrok
* Vagrant share

### Protect non-production servers with HTTP Auth

Basic Auth could be used as the main form of authentication for very simple apps, or admin backends. It is often used to prevent access to staging servers by strangers and search engines (to prevent indexing of non-production pages).

In Rails, the simplest basic auth could be added like this:

```ruby
class ApplicationController < ActionController::Base
  http_basic_authenticate_with name: "admin", password: "hunter2"
end
```

More advanced ways can be found in the [Rails docs](http://api.rubyonrails.org/classes/ActionController/HttpAuthentication/Basic.html).

In any other Rack based server, you can use the `Rack::Auth::Basic` middleware:

```ruby
use Rack::Auth::Basic, "Restricted Area" do |username, password|
  [username, password] == ['admin', 'pass']
end
```
