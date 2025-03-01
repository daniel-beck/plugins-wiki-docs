Send build artifacts to a windows share (CIFS/SMB/samba)

| Plugin Information                                                                                              |
|-----------------------------------------------------------------------------------------------------------------|
| View Publish Over CIFS [on the plugin site](https://plugins.jenkins.io/publish-over-cifs) for more information. |

Older versions of this plugin may not be safe to use. Please review the
following warnings before using an older version:

-   [CSRF vulnerability and missing permission
    checks](https://jenkins.io/security/advisory/2018-07-30/#SECURITY-975)

**This plugin is up for adoption.** Want to help improve this plugin?
[Click here to learn
more](http://localhost:8085/display/JENKINS/Adopt+a+Plugin "Adopt a Plugin")!

# Publish Over ...

Read Publish Over ... wiki page first

Please read [Publish
Over](http://localhost:8085/display/JENKINS/Publish+Over) first.  
Common configuration options that are documented in the Publish Over ...
wiki page will not be repeated here.

[Features](http://localhost:8085/display/JENKINS/Publish+Over+CIFS+Plugin#PublishOverCIFSPlugin-features)  
[Configure](http://localhost:8085/display/JENKINS/Publish+Over+CIFS+Plugin#PublishOverCIFSPlugin-configuration)  
[Change
log](http://localhost:8085/display/JENKINS/Publish+Over+CIFS+Plugin#PublishOverCIFSPlugin-changelog)

# Features

-   Send files to windows shares
-   The plugin is "promotion aware" see
    [Promotions](http://localhost:8085/display/JENKINS/Publish+Over#PublishOver-promotions)
-   Publish to multiple shares in the "Post-build Actions"
-   Passwords are encrypted in the configuration files and in the UI
-   Copy files to a windows share during a build

# Configure

#### Configure a WINS server

From the Jenkins home page, click "Manage Jenkins" and the click on
"Configure System"

In the main Jenkins configuration page, there will be a "Publish Over
CIFS" checkbox in the "Global properties" section.

![](docs/images/cifs_node_props_global.png)

###### WINS server

Set this option to the IP address of a WINS server that will be used by
the Jenkins master, and will be the default for all other nodes (slaves)

The WINS server can be set or overridden for individual nodes (slaves)  
A "Publish Over CIFS" checkbox will appear under "Node Properties" in
the configuration for a node.  
Set the WINS server to an IP address that this node will use for name
resolution.  
If a default WINS server has been specified in the "Global properties",
a node can be configured to not use WINS by checking the "Publish Over
CIFS" property and leaving the WINS server empty.

#### Create host configurations in the main Jenkins configuration

From the Jenkins home page, click "Manage Jenkins" and the click on
"Configure System"

Find the CIFS section (as below) and click on the "Add" button next to
"CIFS Servers"

![](docs/images/cifs_global_unconfigured.png)

You should now have the configuration options as below

![](docs/images/cifs_global_configured.png)

Fill in Name, Hostname, Username, Password and Share. [see Publish Over
... for common options for Host
Configurations](http://localhost:8085/display/JENKINS/Publish+Over#PublishOver-host)

###### Hostname

Hostname is the hostname, IP address or windows servername of the host
that contains the share

###### Username

To specify a user in a specific windows domain, use a back slash to
separate eg MYDOMAIN\\myuser

###### Share

The share is equivalent to the standard Remote directory option, except
that the Share is required and there is no concept of the directories
being relative.  
The share must be, or begin with, a windows share name on the server
named in Hostname.

##### Advanced

If you click the "Advanced..." button for a configuration, then you will
make more configuration options available (see below)

![](docs/images/cifs_global_advanced.png)

[see Publish Over ... for common options for Host
Configurations](http://localhost:8085/display/JENKINS/Publish+Over#PublishOver-host)

##### Click "Test Configuration".

##### Add more server configurations (if required)

##### Save

#### Send files to a windows share during a build

This plugin adds a build step to enable you to send files to a windows
share during a build.

Select "Send files to a windows share" from the "Add build step" drop
down (pic below) and then configure just like [Configure a job to send
files to a windows
share](http://localhost:8085/display/JENKINS/Publish+Over+CIFS+Plugin#PublishOverCIFSPlugin-configjob)
below

![](docs/images/cifs_builder.png)

#### Configure a job to send files to a windows share

Open a jobs main page and then click "Configure" from the left hand
menu.

Find the "Send build artifacts to a windows share" checkbox in the
"Post-build Actions" section and click in the box.

![](docs/images/cifs_unconfigured.png)

You should now have the configuration options as below

![](docs/images/cifs_configured.png)

[see Publish Over ... for common options for
Server](http://localhost:8085/display/JENKINS/Publish+Over#PublishOver-server)

[see Publish Over ... for common options for Transfer
Sets](http://localhost:8085/display/JENKINS/Publish+Over#PublishOver-transfer)

Source files

The build will fail if you do not select any Source files to transfer

##### Advanced (Transfer Sets)

If you click the "Advanced..." button for a Transfer Set, then you will
make more configuration options available (see below)  
![](docs/images/cifs_advanced.png)

[see Publish Over ... for common options for Transfer
Sets](http://localhost:8085/display/JENKINS/Publish+Over#PublishOver-transfer)

###### Clean remote

Delete all files and directories from the remote directory before
uploading the new files.

##### Advanced (Publisher)

If you click the "Advanced..." button that is immediately below the "Add
Server" button, then you will make more configuration options available
(see below)  
![](docs/images/cifs_publisher_advanced.png)

[see Publish Over ... for common options for
Publisher](http://localhost:8085/display/JENKINS/Publish+Over#PublishOver-publisher)

#### Options to override the default Promotion behaviour

If you are configuring an action in a promotion, new options will become
available.  
![](docs/images/cifs_promotions.png)

[see Publish Over ... for common options for
Promotions](http://localhost:8085/display/JENKINS/Publish+Over#PublishOver-promotions)

# Change log

#### 0.11 (2018-07-30)

-   [Fix security
    issue](https://jenkins.io/security/advisory/2018-07-30/#SECURITY-975)

#### 0.9

-   Fixed issue with parameter verification using incorrect check urls
-   Fixed issue with bufferSize not being set correctly on ugprade
    ([issue
    49010](https://issues.jenkins-ci.org/browse/JENKINS-49010))  
      

Questions, Comments, Bugs and Feature Requests

Please post questions or comments about this plugin to the [Jenkins User
mailing list](http://jenkins-ci.org/content/mailing-lists).  
To report a bug or request an enhancement to this plugin please [create
a ticket in
JIRA](https://issues.jenkins-ci.org/browse/JENKINS/component/15850).
