---
layout: post
title: "Riding on Rails3 with a full stack of gems"
date: 2011-08-12 19:02
comments: true
categories: 
---

It's been close to a year since Rails3 came out. Luckily, I've worked on several Rails3 projects after it's released, so I'd like to share a stack of gems that I used in my previous projects. I guess they will give people a bit help while developing a new Rails3 app.

I don't want to explain too much on these gems separately, well, most of the gems have good documents on their project wiki(every great gem should be well documented, right?). Instead, I just add regarding links to their repos so that you'd better take a further look while you really use it. In order to introduce the lists of gems clearly, I simply categorized them based on a rough structure. 

Ok, here we start:

#### **&raquo; Authentication**
>- OmniAuth (<https://github.com/intridea/omniauth>)
>- Devise (<https://github.com/plataformatec/devise>)

The above two are really amazing gems to speed up your authentication. Yes, I love both of them in different cases: ideally OmniAuth is better for applications which want to support multi-provider external authentication, so I've just added OmniAuth into RefactorMyCode Rails3 branch to take its auth benefits; Devise is totally powerful enough for classic authentication case. However, if you have too much your own business logic inside your login/registration/auth flow, you definitely need to make your own authentication. 

#### **&raquo; Access Control**
>- CanCan (<https://github.com/ryanb/cancan>)
>- declarative_authorization (<https://github.com/stffn/declarative_authorization>)

[Ryan](https://github.com/ryanb) is a star in Rails world, so his CanCan is really popular, which aims to do neat but powerful authorization. However, the declarative_autharization is also an option, actually, Ryan mentioned CanCan was inspired by declarative_autharization. 

#### **&raquo; Views/Page and Admin Scaffold**
>- compass (<https://github.com/chriseppstein/compass>)
>- haml (<https://github.com/nex3/haml>)
>- sanitize (<https://github.com/rgrove/sanitize>)
>- rails_admin (<https://github.com/sferik/rails_admin>)
>- web-app-theme (<https://github.com/andreferraro/web-app-theme>)

From a front-end perspective, I suggest you might need to try above gems to speed up and simplify your UI designing. For example on the admin section, it'd be great if you can apply your CRUD quickly to pages, that's what rails_admin does. Surely, these gems won't end all your UI problems, but it really helps when you doing prototype or being lack of some real designers. 

#### **&raquo; Quick SNS**
>- acts-as-taggable-on (<https://github.com/mbleigh/acts-as-taggable-on>)
>- has_friends-rails3 (<https://github.com/rrouse/has_friends>)
>- acts_as_favable (<https://github.com/yorzi/acts_as_favable>)
>- thumbs_up (<https://github.com/brady8/thumbs_up>)
>- acts_as_commentable (<https://github.com/jackdempsey/acts_as_commentable>)
>- profanity_filter (<https://github.com/intridea/profanity_filter>)

Well, I don't mean a whole solution of SNS or regarding feature, here theses gems can help you add the basic cross-object function rapidly, it increases your confidence to focus on designing over programming at the very beginning. Here I want to give a simple introduction to **acts_as_favable**, it allows for favorites refer to be added to multiple and different models.

#### **&raquo; Form and Related Tools**
>- simple_form (<https://github.com/plataformatec/simple_form>)
>- formtastic (<https://github.com/justinfrench/formtastic>)
>- formtastic_datepicker_inputs (<https://github.com/demersus/formtastic_datepicker_inputs>)
>- tiny_mce (<https://github.com/kete/tiny_mce>)
>- paperclip (<https://github.com/thoughtbot/paperclip>)
>- carrierwave (<https://github.com/jnicklas/carrierwave>)

Most of above gems are famous through <railscasts.com> created by Ryan. There are two pairs of options here: **simple_form** and **formtastic** / **paperclip** and **carrierwave**. I like all these solutions, you should pick up one to fit your project, if you want to know differences between each pair, get more details on their wiki :) Tiny is an HUGE gem for rich editing, I list it here to remind its exist, but I recommend you  get the WYSWYG via some JS lib like [CLEditor](http://premiumsoftware.net/cleditor), it works gracefully.   

#### **&raquo; Searching Solutions**
>- meta_seach (<https://github.com/ernie/meta_search>)
>- meta_where (<https://github.com/ernie/meta_where>)
>- thinking-sphinx (<https://github.com/freelancing-god/thinking-sphinx>)
>- acts_at_indexed (<https://github.com/dougal/acts_as_indexed>)
>- sunspot (<https://github.com/outoftime/sunspot>)

Talking about searching in rails, I think you have many words to say. Here I wanna roughly split these gems into two types: Object-based searching and Full-Text searching. I heavily recommend you use meta_search and/or meta_where as your model based searching, it can convert your form params directly to a search solution, that's convenient. Full-Test searching depends on your case, but all these three gems(thinking-sphinx, acts_as_indexed, sunspot) are great. 

#### **&raquo; Pagination**
>- kaminari (<https://github.com/amatsuda/kaminari>)
>- kaminari_themes (<https://github.com/amatsuda/kaminari_themes>)

No more will_paginate in Rails3, absolutely, the only option is kaminari.

#### **&raquo; Background Work**
>- delayed_job (<https://github.com/collectiveidea/delayed_job>)
>- resque (<https://github.com/defunkt/resque>)

There is one post to introduce resque clearly [here](https://github.com/blog/542-introducing-resque), in that post, github staff mentioned their brief history of doing background jobs, so I think you can understand well the differences between delayed_job and resque solution.

#### **&raquo; Status Machine**
>- workflow (<https://github.com/ryan-allen/workflow>)
- state_machine (<https://github.com/pluginaweek/state_machine>)

I like to use workflow a bit more, since it's much natural to me, you definitely need one status machine to control your stable flow stuff, such as a registration flow status or a wizard-like features.

#### **&raquo; Rack API framework**
>- grape (<https://github.com/intridea/grape>)

This gem is for adding API to Rails/Sinatra application. [Michael](http://intridea.com/about/people/mbleigh) gave people an awesome [speech in RubyConf2010](http://confreaks.net/videos/475-rubyconf2010-the-grapes-of-rapid) on his Grape, here I suggest you should watch it to know more details about GRAPE. I believe you will fall in love with it.

#### **&raquo; Memcached Client**
>- memcache-client (<https://github.com/mperham/memcache-client>)
>- dalli (<https://github.com/mperham/dalli>)

These two gems are actually mainly written by one same author _[Mike Perham](https://github.com/mperham)_, he mentioned that _Dalli is a high performance pure Ruby client for accessing memcached servers. It works with memcached 1.4+ only as it uses the newer binary protocol. It should be considered a replacement for the memcache-client gem. The API tries to be mostly compatible with memcache-client with the goal being to make it a drop-in replacement for Rails._

#### **&raquo; Deployment and Monitor**
>- capistrano (<https://github.com/capistrano/capistrano>)
>- cap-recipes (<https://github.com/nesquena/cap-recipes>)
>- god (<https://github.com/mojombo/god>)

I am not a system administrator, so every time talking about the regarding aspects will make me feel silly, I just try to describe tools which can help me out on unfamiliar area, that's not bad, at least people like me, will do deployment and monitor quickly based on these gems, they do help. 

#### **&raquo; Cron job and Backup as a Pro**
>- whenever (<https://github.com/javan/whenever>)
>- backup (<https://github.com/meskyanichi/backup>)

Above two gems are my favorites, before knowing these two gems, I have to write complex and stupid scripts to do backups that I am not familiar with. Cron job is also a pain in ass if you are not a system administrator. Now time changes, you, as a ruby programmer, can do the corn job and backup in ruby way, surely as a PRO. :)  

#### **&raquo; Testing Gracefully**
>- rspec-rails (<https://github.com/dchelimsky/rspec-rails>)
>- factory_girl_rails (<https://github.com/thoughtbot/factory_girl_rails>)
>- faker (<https://github.com/yyyc514/faker>)
>- watchr (<https://github.com/mynyml/watchr>)
>- autowatchr (<https://github.com/viking/autowatchr>)
>- database_cleaner (<https://github.com/bmabey/database_cleaner>)
>- mail_safe (<https://github.com/myronmarston/mail_safe>)

Testing is always important, I know TDD and BDD are getting more and more popular, that means you have to own your super gun to make it happen. Right, here is a list of gems which can help you out, I didn't cover all different levels of testing with these gems. Point is, rspec is my favorite framework for testing, **factory_girl** and **faker** are good supports. Anyway, test by your way.

#### **&raquo; Toolkit**
>- ruby-debug (<https://github.com/mark-moseley/ruby-debug>)
>- hirb (<https://github.com/cldwalker/hirb>)
>- cheat (<https://github.com/defunkt/cheat>)
>- rails-settings-cached (https://github.com/huacnlee/rails-settings-cached)

There are many handy gems which will give you convenience and power. Take above four as examples, ruby-debuy gives you a chance to check your running applications' context at specific program point; hirb display your AR items in table view in console; cheat makes your terminal working as a pool of other gems' manual; rails-settings-cached is for global configurations in Rails3 application. Yeah, throwing the brick out is to meet your GEMS.

### **How to find great gems?**
First, you need to follow up Ryan's [railscasts](railscasts.com), he is good at introducing new stuff in video. Second, you can go through great open source project's **Gemfile**, yeah, it's definitely the best way to come across valuable gems. Third, just subscribe [github ruby trends](https://github.com/languages/Ruby) to know what's going on in Ruby/Rails community. There are also some other involving sites, like [rubygems](rubygems.org) and [railsplugins](railsplugins.org), you should take a glance when you free, I bet you will find useful gems.


It's nearly the end of this post, this topic was originally shared with all Intridea China Team members during last Friday Teahour. You can find the PPT [here](http://www.slideshare.net/yorzi/riding-on-rails3-with-full-stack-of-gems). To share with more people, I turn it into this blog, I must miss many valuable gems in this list, so please comment your thoughts.