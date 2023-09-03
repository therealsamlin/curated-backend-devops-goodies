# List-of-Goodies

## Web Scrapers
##### screen scraping and web crawling library for PHP. Supports HTML/XML
https://github.com/FriendsOfPHP/Goutte

## Browser Tools

##### Syntax highlighting on chrome for bitbucket
https://chrome.google.com/webstore/detail/refined-bitbucket/afppminkfnfngihdocacbgeajbbdklkf

##### Browser push notifications using JavaScript
https://medium.com/front-end-hacking/browser-push-notifications-using-javascript-10453a78110#.2hyy29zg1

## Backend
##### API Blueprint tester - mocks as server from your api blueprint documentation
https://www.npmjs.com/package/drakov

### 17 Tips for Using Composer Efficiently
https://blog.martinhujer.cz/17-tips-for-using-composer-efficiently/

### Optimisation
##### Composer autoload optimisation
https://getcomposer.org/doc/articles/autoloader-optimization.md

##### PHP cache optimisation
https://github.com/appstract/laravel-opcache
https://medium.com/appstract/make-your-laravel-app-fly-with-php-opcache-9948db2a5f93

### Books
##### Microservice Architecture - Irakli Nadareishvili, Ronnie Mitra, Matt McLarty & Mike Amundsen

### vhost
##### General Nginx Knowledge
Understanding Nginx Server and Location Block Selection Algorithms
https://www.digitalocean.com/community/tutorials/understanding-nginx-server-and-location-block-selection-algorithms

##### Understanding and Implementing FastCGI Proxying in Nginx
https://www.digitalocean.com/community/tutorials/understanding-and-implementing-fastcgi-proxying-in-nginx

### Manage node version
https://github.com/tj/n

## Frontend Knowledge
### Image optimisation 
https://imageoptim.com/mac

##### Visual guide to CSS
http://cssreference.io/

## Testing
##### Generates php code graph to pinpoint bottleneck of the app. Mainly used to enhance app performance.
https://blackfire.io/

##### Stress testing (completely free)
http://www.hecticgeek.com/2012/11/stress-test-your-ubuntu-computer-with-stress/

##### Stress testing/ Load testing (more comprehensive, free for one host)
http://loader.io/

#### Email testing
https://mailtrap.io/

## DevOps

##### Memory & CPU consumption monitoring in Linux
http://dag.wiee.rs/home-made/dstat/

##### AWS in Plain English
https://www.expeditedssl.com/aws-in-plain-english

##### AWS complete guide
https://github.com/open-guides/og-aws

##### Database refactoring - for continue integration and 0 downtime for database migration
http://databaserefactoring.com


#### Ubuntu Auto Upgrade - security packaged 
##### Install
`sudo apt-get install unattended-upgrades apt-listchanges`
##### Reconfigure
`sudo dpkg-reconfigure -plow unattended-upgrades`
##### Update config files
```
/etc/apt/apt.conf.d/20auto-upgrades
APT::Periodic::Update-Package-Lists "1";
APT::Periodic::Download-Upgradeable-Packages "1";
APT::Periodic::Unattended-Upgrade "1";
APT::Periodic::AutocleanInterval "7";
```
##### If auto reboot on a day by day basis is acceptable, then uncomment the following lines and update appropriately.
```
/etc/apt/apt.conf.d/50unattended-upgrades
Unattended-Upgrade::Automatic-Reboot "true";
Unattended-Upgrade::Automatic-Reboot-Time "01:00";
```

##### If it isn't, then instead create a cron job to reboot as often as you'd like updates installed. In this case, we'd recommend once a week (http://www.cronmaker.com/)
```
#launch cron manager for root
sudo crontab -e
 
#install a reboot to run once a week on Sunday at 1am.
0 1 * * 0 /sbin/reboot -h
```

## Linux

Linux commands mindmap
![linux commands](img/linux-xmind.png)
https://xmind.app/m/WwtB/



## Plugins

##### Intercom - plug and play chat app for websites
https://www.intercom.com/


## Graphing Tools
##### creates ascii graph by dragging lines
http://asciiflow.com/

##### draws ASCII diagrams that allows you to paste it in a comment block or readme file
https://monodraw.helftone.com/
```
                    ┌─────────────────────────┐
                    │Sources: Statsd, Collectd│
                    │          etc.           │
                    └─────────────────────────┘
                                 │
                                 ▼
 ┌ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─
                             AWS ELB                            │
 └ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─
                                 │
             ┌───────────────────┴───────────────────┐
             ▼                                       ▼
 ┌───────────────────────┐               ┌───────────────────────┐
 │                       │               │                       │
 │       Polymur A       │               │       Polymur B       │
 │                       │               │                       │
 └───────────────────────┘               └───────────────────────┘
             │                                       │
             ├───────────────────────────────────────┤
             ▼                                       ▼
 ┌───────────────────────┐               ┌───────────────────────┐
 │                       │               │                       │
 │      Graphite A       │◀─────────────▶│      Graphite B       │
 │                       │               │                       │
 └───────────────────────┘               └───────────────────────┘
             ▲                                       ▲
             └───────────────────┬───────────────────┘
                                 │
 ┌ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─
                             AWS ELB                            │
 └ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─
                                 ▲
                                 │
                 ┌───────────────────────────────┐
                 │                               │
                 │            Grafana            │
                 │                               │
                 └───────────────────────────────┘
```


## Frontend

##### Datepicker - flatpickr with themes and mobile support
https://chmln.github.io/flatpickr/

##### Cute avatar generator for frontend demo
http://avatars.adorable.io

## Analytics

##### Covers the following.
* Loading analytics.js
* Tracking custom data
* Error tracking
* Performance tracking
* Using autotrack plugins
* Testing your implementation
* Filtering out local/spam data
* Reporting and visualizing your data
https://philipwalton.com/articles/the-google-analytics-setup-i-use-on-every-site-i-build/

## Kubernetes

##### Lens IDE

Lens is a kubernetes IDE made by Kontena, Inc. It's an open-source application that runs on macOS, Linux, and Windows

Ever since I've discovered Lens I've been using it religiously, so far I'm around 6 months into using the tool and the experience has been phenomenal 

There are 2 available themes for Lens: 

1. Light theme
2. Dark theme

Personally I like the dark theme, it kinda reminds me of discord, the user experience is great and self-explanatory


Lens has multi-cluster support which is super useful, allegedly you can run hundreds of clusters at the same time 
which is a great feature and saves time from switching in abetween context

At a quick glance you have all the resources available at the left hand bar, from pods to deployments, 
from configmaps to service.

You'd even get a list of custom resources available to choose from.

Going into the pod section, Lens allows you to view logs of the containers and attach to it, 
if you have a lot of pods in the cluster you can filter by namespace and search on keywords

You'd also be able to edit resources on the fly, which is really useful if you're quickly updating a change 
esp for quick testing purposes.

With the CRD section if you're running istio on your cluster you'd be able to Edit your virtualservices entry too


Overall I really like this tool and it has greatly boosted my efficiency while working with kubernetes clusters. 





## General
##### Phpstorm tips
http://phpstorm.tips/tips

##### Becoming a better programmer
http://jlongster.com/How-I-Became-Better-Programmer

##### Review/Usage of techonologies out in the market
http://stackshare.io/

##### List of Computer Science courses with video lectures.
https://github.com/Developer-Y/cs-video-courses

##### Take screenshot of site in dimension specified
https://github.com/sindresorhus/pageres-cli

##### Performance Management Tool
OKRs and performance management app
https://7geese.com/

##### Presentation Tool (mac)
https://www.decksetapp.com/

##### 100k emails for free - sparkpost
https://www.sparkpost.com/pricing/
