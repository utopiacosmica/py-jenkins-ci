# PyJenkinsCI
=========

PyJenkinsCI is a test Jenkins Continuous Integration (CI) for Python projects,
compatible with Mac OSX and Ubuntu systems. This project runs standard code
quality checks, and a JMeter stress performance test. ***This project should not
be deployed into production!!!*** It is for demonstration and learning uses
only.

<iframe width="560" height="315" src="https://www.youtube.com/embed/WJb1U4mlK7s" frameborder="0" allowfullscreen></iframe>

## Run test project
- use a Mac, or Ubuntu system
- enable remote SSH access
- install [VirtualBox](https://www.virtualbox.org/wiki/Downloads) and [Vagrant](https://www.vagrantup.com/downloads.html)
- git clone project into "~/Sites" folder
- configure the ssh HOST_USER and HOST_PASS in "/data/build.sh"
- open a Terminal, cd "/vagrant", run "vagrant up"
- wait for provisioning to finish, usually 2 to 10 minutes
- open browser, go to "http://127.0.0.1:8080"
- click on "discover-flask-vagrant"
- click "Build Now"
- wait for project to build

## Video
[https://www.youtube.com/watch?v=WJb1U4mlK7s](https://www.youtube.com/watch?v=WJb1U4mlK7s)

## To Do:
- add Gauntlt
- add Windows Host support
- add Selenium, WebDriver, and Protractor
- add Snort
- add Nagios

<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>
<br/>

## Add Another Jenkins Project

If you would like to add your own project, here are the steps to take:

***Create New Project***
- Item name: discover-flask-vagrant
- Freestyle Project

***Source Code Management***
- Source Code Management: Git
- Repository URL: https://github.com/apolloclark/discover-flask-vagrant

### Build
- "Add build step"
- Execute shell
- Command: "sh /vagrant/build.sh"

### Post-build Actions
***Report Violations***
- pylint: **/pylint.out

***Publish JUnit test result report***
- Test report XMLs: **/nosetests.xml

***Public Cobertura Coverage Report***
- Cobertura xml report pattern: **/coverage.xml

***Publish SLOCCount analysis results***
- SLOCCount reports: **/sloccount.sc

***Publish Performance test result report***
- Add a new report > JMeter
- Report files: **/jmeter.jtl

***Save***

***Update pathways in build.sh***

***Add "/www/run_tests.sh" script to project***

***Build Now***

***Enjoy the show!***

***References***

- http://www.alexconrad.org/2011/10/jenkins-and-python.html
- http://bhfsteve.blogspot.com/2012/04/automated-python-unit-testing-code_27.html
- http://www.wallix.org/2011/06/29/how-to-use-jenkins-for-python-development/