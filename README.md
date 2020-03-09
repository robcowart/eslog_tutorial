# From Raw Logs to Real Insights

I have a lot of passion for the Elastic Stack and the things it enables its users to achieve with their data. However the path to getting to this point was longer for me than it needed to be. With this tutorial material I am hoping to help make the same path shorter for others. So ...

## if you want to know how to turn this...

`<5>Oct 18 12:57:30 BRDC-2 kernel: [BlackRidge|Gateway|3.0.0.4619] class="Attribution" category="Unknown Identity" ctx="bump0" src="125.33.12.234" srcPort="25654" dest="5.149.112.53" destPort="23" identity="honeypot2Id" gwAction="DISCARD" gwMode="Monitor"`

## into this...

![dashboards](https://user-images.githubusercontent.com/10326954/32144162-f1f923fa-bcb4-11e7-834a-65ac1c87d4a8.png)

## this tutorial is for you!

Back when I began my journey with the Elastic Stack I quickly discovered that while the online documentation provides a wealth of reference material, there was little that described what those first few steps should be. Online I found very little that covered more than the most basic tasks. Eventually as I stumbled upon more and more hints and tips, slowly things fell in place. Finally one day it really "clicked", and I have been enjoying the benefits of working with data in the Elastic Stack ever since. This tutorial follows very closely the exact path traveled as I took my first steps. I hope you find it helpful.

**NOTE: The tutorial does not cover installing the Elastic Stack itself. This is covered well in the documentation. You will need Elasticsearch, Logstash and Kibana. Version 5.6.3 was used while creating this tutorial, but most versions should work fine.**

The PDF file is the slide deck that I use to present the tutorial, although everything can also be presented using a live system. In fact the Kibana slides mostly provide examples, but by loading the dashboards from `kibana/blackridge.kibana.json` you can investigate how each visualization and dashboard was defined.

The files named `logstash/##_blackridge.logstash.conf` correspond to the step for building the pipeline in the slides. I encourage you to tryout each step for yourself and notice how each enhancement adds value to the raw data. The `conf.d` directory includes the final pipeline split into multiple files, demonstrating how you can keep the parts of a pipeline more managable by breaking it into multiple blocks of code.

The `logs` directory includes two files. `dev.syslog` contains a single syslog message that will be used as we develop the Logstash pipeline. `data.syslog` will be loaded once the pipeline is complete. It contains seven days of data, which we can analyze using Kibana dashboards.

If you find this material helpful or have any recommended improvements I would appreciate hearing your feedback.

## Getting started with the Elastic Stack

If you are new to the Elastic Stack, this video goes beyond a simple default installation of Elasticsearch and Kibana. It discusses real-world best practices for hardware sizing and configuration, providing production-level performance and reliability.

[![0003_es_install](https://user-images.githubusercontent.com/10326954/76195457-9ea2d580-61e8-11ea-8578-8fb39908afec.png)](https://www.youtube.com/watch?v=gZb7HpVOges)

Additionally local SSD storage should be considered as _*mandatory*_! For an in-depth look at how different storage options compare, and in particular how bad HDD-based storage is for Elasticsearch (even in multi-drive RAID0 configurations) you should watch this video...

[![0001_es_storage](https://user-images.githubusercontent.com/10326954/76195348-61d6de80-61e8-11ea-951d-1694d2e0392b.png)](https://www.youtube.com/watch?v=nKUpfJCBiS4)
