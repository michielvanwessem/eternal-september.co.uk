---
layout: page
title: Resume
cover: 'assets/images/cover-pen.jpg'
navigation: true
logo: 'assets/images/ghost.png'
current: resume
---
<a name="index"></a>
<div style="text-align:center" markdown="1">
## Michiel van Wessem<br />
##### System-administrator / DevOps-Engineer / Cloud solution Architect<br />

![Michiel van Wessem](/assets/images/michiel.png)

<a name="index"></a>
&nbsp;
#### Table of contents
[Exprerience ](#experience)
&nbsp; &nbsp; &nbsp;
[Education](education)
&nbsp; &nbsp; &nbsp;
[Certification](#certification)
<br>
[Skills](#skills)
&nbsp; &nbsp; &nbsp;
[Languages](#languages)
&nbsp; &nbsp; &nbsp;
[Publications](#publications)
<br>
[Extra curricular activities](#misc)
&nbsp;
</div>


#### Profile

I am an experienced server/system administrator with experience of Linux Server maintenance and security, working with Debian, Ubuntu, CentOS, and Red Hat Linux. In my role at Adaptive I gained experience with deploying scalable, high availability solutions for both my employer, as well as clients, advising them on how to apply new technology, as well as keeping them appraised of methods to help them lower their total cost of ownership.

During my time at Hive Online and Hive IP Ltd, I have build on that knowledge, moving their entire platform from Rackspace over Amazon Web Services, creating a more cost effective and stable infrastructure. Over the years working with Amazon Web Services I have come to love the flexibility and the range of tools that Amazon provides for hosting platforms. 

In my current role as system-administrator (previously as an DevOps-Engineer) my focus is largely aimed at the Operations side of the business. On a day to day basis, I work closely with a small group of Python and Django developers, supporting them in rolling out and setting up servers with bespoke written tools. The platform runs a combination of nginx, celery service, and a MySQL backend, with either RabbitMQ or AWS SQS. As of late, I have found myself taking more project orientated tasks, including keeping track of project schedules, as well as dealing more with clients on a day to day basis.

Our client solutions are hosted within cloud based environments either in Amazon Web Services, or Rackspace Cloud. I work closely with our developers and project management teams to ensure the servers are deployed in a timely fashion, maintain them while running, and remove them when our client’s promotion has ended.

Part of my remit when taking this role was to move our current infrastructure from Rackspace into Amazon Web Services, to deliver a more efficient, cost-effective and competitive hosting solution for their web services, adapting the solutions where needed to best suit their needs.

In previous roles, I have worked with traditional LAMP stacks and supported Drupal developers. As a systems administrator, I ensure that the technical infrastructure is continually stable and secure. This includes disaster recovery, patching and securing access, backups, automation, documenting and continuous monitoring of the infrastructure, as well as out of hours support.

For future roles, I would like to increase my knowledge and understanding of Amazon Web Services and build upon my existing experiences. Aside from that I have developed an interest in technical project management roles and would love to branch myself out in that direction, all the while keeping my technical expertise on par. In brief, I am an eager, motivated and multi-disciplined person, that loves to learn and is interested in following the process from the stages of design, through planning and detailing, to the successful completion.

[References](https://eternal-september.co.uk/contact/) can be supplied upon request.

[A PDF copy](https://drive.google.com/open?id=1dMCxLmYq8CsZjhIG12V8RWzwaixH7K8x) of this CV can be downloaded from here.


<p style="text-align:right" markown="1">
  <a href="#index">...back to top</a>
  &nbsp;
</p>
  
--------------

<a name="experience"></a>
#### Professional experience

<table>
  <tbody>
  
  <tr bgcolor="#f1f1f1">
    <th width='30%' style="vertical-align:top" style="table-layout:fixed">26/04/2017 - current<br></th>
    <th>System Administrator, Hive IP Ltd.<br></th>
  </tr>
  <tr>
    <td></td>
    <td>
      <em>(Restart of Hive Online Ltd, with little change in current role as described)</em>
      <br><br>
      <li>Writing and deployment of Saltstack for configuration management to manage our server configuration in a scalable, and consistent state. This led to a 70-90% reduction in configuration files needing to be kept.</li>
      <li>Write AWS CloudFormation templates to facilitate to spin up server instances via `Infrastructure as Code' (IaC).</li>
      <li>Design, document, and plan a cloud to cloud migration, including technical design, documentation, and orchestration.</li>
      <li>Developed custom scripts to automate provisioning, deployments, and maintenance task.</li>
      <li>Create a hybrid fallback solution consisting of cross cloud MySQL and RDS Replication, including delayed replicating servers.</li>
      <li>Migrate the current infrastructure within Rackspace to Amazon Web Services, in many cases without noticeable downtime to our clients</li>
      <li>Helped to facilitate project management, chaired strategic sessions, and create more visibility in our current running projects.</li>
      <li>Provided monthly cost overview, set against the total costs of our cloud operations, to highlight diminishing costs.</li>
      <li>Deal with clients as main technical point of contact and manage their expectations.</li>
      <li>Liased with developpers to agree and arrange technical duty out of hours rota.</li>
    </td>
  </tr>
  

  <tr bgcolor="#f1f1f1">
    <th width='30%' style="vertical-align:top">11/2016 - 03/2017<br></th>
    <th>DevOps - Engineer, Hive Online Ltd.<br></th>
  </tr>
  <tr>
    <td></td>
    <td>
      (<em>Hive Online Ltd stopped trading in March 2017 and restarted as Hive IP Ltd</em>)
      <br><br>
      <li> Maintain, manage, and support for client environments in Rackspace Cloud, as well as Amazon Web Services. Servers are running CentOS Linux to server django based sites under nginx with uWSGI, and a MySQL backend.</li>
      <li> Migration from Rackspace dedicated, and Rackspace Cloud into Amazon Web Services.</li>
      <li> Migration and rolling out of clients into AWS using AWS Container Services.</li>
      <li> Liaise and engage with Rackspace, Pythian (third party DBa's) to provide ongoing support for our client environments.</li>
      <li> Roll out automated testing of code, through Jenkins CI, with automated Jenkins workers created on demand in AWS</li>
      <li> Wrote a bespoke DNS disaster recovery script in python, decreasing time to recover from a DNS outage significantly. </li>
      <li> Documenting our infrastructure, and processes for a third party managed ops company documentation. Maintain contact and lead (technical) conversations with a view of outsourcing part of the company's infrastructure. </li>
    </td>
  </tr>

  <tr bgcolor="#f1f1f1">
    <th width='30%' style="vertical-align:top">03/2015 - 10/2016<br></th>
    <th>Linux Server Administrator and AWS Solutions Architect, Adaptive Web Ltd.<br></th>
  </tr>
  <tr>
    <td></td>
    <td>
      My remit at Adaptive was to assist the in-house development team, and Drupal support team in a long range of task, including deployment, go live, system design. Responsible for backup strategy and disaster recovery, uptime, security, and stability of our own cloud based  infrastructure, as well of various clients.
      <br><br>
      <li> Support and maintain Legacy servers. Project lead in migrating away from dedicated services to cloud based infrastructures.</li>
      <li> Create, maintain and support clients infrastructure in both Amazon Web Services and Microsoft Azure Cloud.</li>
      <li> Secure and maintain Linux web servers for serving Drupal websites with Apache/NINGX, MySQL/MARIADB and PHP5 stack. </li>
      <li> Procuring, establishing, and maintaining a stratum 1 and stratum 2 NTP time-servers to accurately serve time to servers, both internally and cloud based.</li>
      <li> Writing scripts for automation; such as deployment of keys through Ansible, automating backups, and retrieval of assets from a third party for use by projects.</li>
      <li> Advising clients on cost saving strategies to lower their TCO.</li>
      <li> Internal roll out of last-pass and two factor authentication support, and continuing effort to increase on site security awareness, and removing of unsecure logins</li>
      <li> Maintaining and supporting internal systems, such as Google Apps Accounts, Asset maintenance and distribution</li>
      <li> Introducing git source-control, point of contact and merge master on a large project.</li>
      <li> Support, maintain, and secure Drupal sites, to assist the in-house Drupal support team.</li>
    </td>
  </tr>


  <tr bgcolor="#f1f1f1">
    <th width='30%' style="vertical-align:top">2004 - 2015<br></th>
    <th>Long term ill health and unemployed.<br></th>
  </tr>
  <tr>
    <td></td>
    <td>
      <em>(Long time off work due to ill health, from which I have fully recovered).</em><br />
      During that time I have kept myself up to date and active by engaging in (amongst others) the following projects:
      <br><br>
      <li> Project administrator and contributor for the Slackbuilds project; an open source project for the Slackware Linux distribution.</li>
      <li> Maintaining small LAN network including scripts to automate cross network backups</li>
      <li> Testing, and learning new distributions,with a focus on Debian and CentOS</li>
      <li> Improvements to mental health through exercise and social interaction.</li>
    </td>
  </tr>


  <tr bgcolor="#f1f1f1">
    <th width='30%' style="vertical-align:top">2003 - 2004<br></th>
    <th>Project Co-ordinator, Computacentre.<br></th>
  </tr>
  <tr>
    <td></td>
    <td>Worked as part of the DWP Account as part of the Refurbishment and Disposal strand of the DWP Digital Office Infrastructure (DOI) Programme.
      <br><br>
      <li>Arrange collection and drop off of equipment at DWP offices.</li>
      <li>Arrange for retrieval and storage of proof-of-delivery and check against project spreadsheet.</li>
      <li>Established and improved the relationship with our dedicated third party courier.</li>
      <li>Outside remit activities consisted of: desktop support, cable patch work in server room, assisting of out of office IT staff with patching and repairing virii struck computers to contain and eradicate virus. Restore data on workstations that were hit by the virus to enable people to keep working.</li>
    </td>
  </tr>
  
  
  <tr bgcolor="#f1f1f1">
    <th width='30%' style="vertical-align:top">2002 - 2003<br></th>
    <th>Temporary work for various UK based agencies.<br></th>
  </tr>
  <tr>
    <td></td>
    <td>
      On Arrival in the UK I worked in various short term temporary work assignments through job agencies.
      <br><br>
      Clients included: Royal Dutch Shell, HSBC (mail room)
    </td>
  </tr>


  <tr bgcolor="#f1f1f1">
    <th width='30%' style="vertical-align:top">2000 - 2002</th>
    <th>Unix System Administrator, Ordina Finance Network and Internet Services.</th>
  </tr>
  <tr>
    <td></td>
    <td>
      <li> Operational maintenance of a three node Sun High Availability Cluster, internal and external firewalls, and development Sun Servers.</li>
      <li> Working with clients to ensure their servers and operating systems are running as agreed within defined SLA's.</li>
      <li> Scripting to automate system tasks, such as clearing core-dumps of the system to enable SAP users to log in.</li>
      <li> Firewall maintenance and monitoring.</li>
      <li> Rolling out monitoring solutions to clients.</li>
      <li> Procurement of hardware from a sister company, and liaising in pick-up and delivery on site.</li>
    </td>
  </tr>
  
  
  <tr bgcolor="#f1f1f1">
    <th width='30%' style="vertical-align:top">1997 - 1998<br></th>
    <th>Principal Consultant, Netmediair, the Netherlands.<br></th>
  </tr>
  <tr>
    <td></td>
    <td>
      Personal limited company, delivering website solutions to clients. 
      <br><br>
      I consulted with clients, delivered business proposals, and assisted companies transitioning from a paper point of presence to a digital one, as well as establishing their digital brand.
    </td>
  </tr>

</tbody>
</table>


<p style="text-align:right" markown="1">
  <a href="#index">...back to top</a>
  &nbsp;
</p>


<a name="education"></a>
#### Education
<table>
<tbody>
  <tr bgcolor="#f1f1f1">
    <th width='30%' style="vertical-align:top">1994 - 2000<br></th>
    <th>
      BA Computing – Digital Media and Communication.<br>
      University of Professional Education, Utrecht, the Netherlands
      </th>
  </tr>
  <tr>
    <td></td>
    <td>
      A four year sandwich course, including  a six month internship.<br>
      The degree is  the equivalent of a 2:1 in the UK. 
      <br><br>
      My dissertation was on the subject of: <em>`security in e-commerce architectures'</em>
      Internship at a digital publisher as IT administrator, service desk, sales, and help file developer. 
      Internetship at ordina insititude for research and innovation
      take part in corperate security forum
      <br><br>
      During my final year, I taught in first year student's courses in web-design. I also taught evening classes for people wanting to be retrained as web designers.
      <br><br>
    </td>
  </tr>


  <tr bgcolor="#f1f1f1">
    <th width='30%' style="vertical-align:top">1991 - 1992</th>
    <th>
      PABO Utrecht, Teacher Training for Primary schools<br>
      University of Professional Education, Utrecht, the Netherlands
    </th>
  </tr>
  <tr>
    <td></td>
    <td></td>
  </tr>


  <tr  bgcolor="#f1f1f1">
    <th width='30%' style="vertical-align:top">1985 - 1991</th>
    <th>
      HAVO<br>
      Rembrandt Scholengemeenschap, Leiden, the Netherlands. 
    </th>
  </tr>
  <tr>
    <td></td>
    <td>Havo (GCSE equivalent) in Dutch, English, Maths, Physics, Chemistry and Business Economics</td>
  </tr>
</tbody>
</table>


<p style="text-align:right" markown="1">
  <a href="#index">...back to top</a>
  &nbsp;
</p>


<a name="certification"></a>
#### Certification / Accreditations

<table>
<tbody>
  <tr bgcolor="#f1f1f1">
    <th width='30%' style="vertical-align:top">May 2016</th>
    <th>AWS TCO and Cloud Economics Accreditation.</th>
  </tr>
  <tr>
    <td></td>
    <td></td>
  </tr>

  <tr bgcolor="#f1f1f1">
    <th width='30%' style="vertical-align:top">December 2015</th>
    <th>AWS Business Professional Accreditation.</th>
  </tr>
  <tr>
    <td></td>
    <td></td>
  </tr>

  <tr bgcolor="#f1f1f1">
    <th width='30%' style="vertical-align:top">May 2015</th>
    <th>AWS Technical Professional Accreditation.</th>
  </tr>
  <tr>
    <td></td>
    <td></td>
  </tr>

  <tr bgcolor="f1f1f1">
    <th width='30%' style="vertical-align:top">December 2000</th>
    <th>Sun Microsystems – Shell scripting for System Administrators.</th>
  </tr>
  <tr>
    <td></td>
    <td></td>
  </tr>

    
</tbody>
</table>


<a name="skills"></a>
<p style="text-align:right" markown="1">
  <a href="#index">...back to top</a>
  &nbsp;
</p>


#### Skills
<u>System administration:</u>

* Linux: Debian, Ubuntu, Red Hat, CentOS, Slackware.
* Webservers: Apache, nginx.
* Databases: MySQL, MariaDB, Sqlite, mongodb.
* Mail Servers: Postfix.
* CI/CD: Jenkins.
* Configuration: CFEngine3, Salt-stack, Ansible.
* Other: Varnish, ntp, memcache, redis.

<u>Amazon Web Services:</u>

* EC2: Elastic Cloud Compute.
* ELB: Elastic Load Balancer.
* RDS: Relational Database Service (MySQL, Aurora), .
* ElastiCache: Memcache, Redis
* S3: Simple Storage Solution.
* Route53: DNS.
* IAM: Identity Access Management.
* VPC: Virtual Private Cloud.
* SNS: Push Notification Service.
* SQS: Simple Queue Service.
* IaC: Cloudformation.
* Trusted Advisor.

<u>Microsoft Azure:</u>

* Virtual Machines.
* Networking.

<u>Rackspace:</u>

* Rackspace Dedicated Services.
* Rackspace Cloud Environment.
* Rackspace DNS/Cloud DNS.
* Rackspace Cloud LoadBalancers.

<u>Development:</u>

* bash scripting, python scripting.
* git, mercurial,svn.
* vim, atom, sublime.
* mysql workbench, mysql-cli..


<p style="text-align:right" markown="1">
  <a href="#index">...back to top</a>
  &nbsp;
</p>


<a name="languages"></a>
#### Languages:

* Native Dutch speaker (ELP rating C2+),
* Near Native English,
* Rudimentary knowledge of French. (ELP rating A2-B1),
* Basic understanding of German.


<p style="text-align:right" markown="1">
  <a href="#index">...back to top</a>
  &nbsp;
</p>


<a name="publications"></a>
### Publications
* The Slack World: A review of slackware-12.0 (2007).
<br><br>
_Originally posted on [The Slack World](http://slackworld.berlios.de/slackware-12.0.html).<br>
Link [[mirrored]]({% link publications/slackware-12-a-review.md %}) locally._


<p style="text-align:right" markown="1">
  <a href="#index">...back to top</a>
  &nbsp;
</p>


<a name="misc"></a>
### Extra curricular activities
*(in progress)*: Learning and becoming more fluent in Python<br />
*(in progress)*: Studying for AWS Certified Solutions Architect Associate Exam.

*(planned)*: Studying for AWS Certified SysOps Administrator<br />
*(planned)*: Increase proficiency in SQL<br />
*(planned)*: PRINCE2 Studies for project management<br />
<br />


<p style="text-align:right" markown="1">
  <a href="#index">...back to top</a>
  &nbsp;
</p>





