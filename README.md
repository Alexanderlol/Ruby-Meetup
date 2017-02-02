#Ruby Meetup
#####Feb 1st 2017
###Real HTTP server
Common choices:  

puma (puma.io)
* multi-thread
* low memory

Unicorn (bogomips.org/unicorn) 

Passenger (phusionpassenger.com)  
* Multi-process, scales up (free)  
* Multi process / multi-thread (paid - not cheap)  

###DB Server additionl costs
$5/month - do everything yourself (digital ocean)  

$20/m AMazon RDS
* automated backups
* autmated atch management
* easy route to higher availability
* easy route to higher performance

####Keep development environment as close as possible to production environment (docker?)

###intro to Dokku (and heroku)
* Dokku - open source clone of heroku
* push application to server with Git
* Dokku runs app in a new container
* if sanity checks pass, manages seamless switching to new version and shut down of old container
* can also run app in multiple containers for scaling

###Cheap version
* cheap host provider for app, amazon RDS for db
* use round robin DNS instead of a load balancer 
(each dns name maps to multiple ip addresses; client should theoretically try next one if one fails)
* scale up manually as req'd
* run freq health checks
