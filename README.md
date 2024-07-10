# Website for Ricgraph - Research in context graph

This repository contains the code and the final published 
website for Ricgraph - Research in context graph. To learn more about
Ricgraph - Research in context graph, go to the 
[Ricgraph GitHub repository](https://github.com/UtrechtUniversity/ricgraph).

To create and maintain the Ricgraph website, the static website CMS 
[Publii](https://getpublii.com/) is used, with theme 
[Editorial-2](https://marketplace.getpublii.com/themes/editorial-2).

You can find the main Ricgraph website on www.ricgraph.eu. Alternative
sites are www.ricgraph.nl and www.ricgraph.com.


### How to install Publii

Read [Download and install Publii](https://getpublii.com/docs/install-publii.html).

### How to configure Publii for the Ricgraph website
* Clone this GitHub repository to your local machine.
* Open Publii.
* In the top right of the Publii window, there are 3 stacked dots.
  Click on it.
* Choose _App settings_.

  In the Files location setting, set the following values:
  * Sites location: set to *[local path to this GitHub repository]/publii-site*
  * Backup location: set to *[local path to this GitHub repository]/publii-backup*
  * Preview location: set to *[local path to this GitHub repository]/publii-preview*
    
  Click "Save your settings" and click "Go back".
* In the _Server_ menu in the left bar of Publii, choose ".zip Manual upload".

  Make sure you have the following settings:
  * Website URL: set "Use relative URLs" *on*.
  * Output type: set to *TAR archive*.
  * Output directory: 
    set to *[local path to this GitHub repository]/ricgraph-website*
* If you click *Sync your website* in the left bar of Publii, 
  the resulting file will be created in 
  output directory *[local path to this GitHub repository]/ricgraph-website*
  with the name *ricgraph-research-in-context-graph-files.tar*.

### Install the Ricgraph website on your webserver
* Login as user *root* on your web server.
* Go to the webserver directory on that server.
  Probably it is in
  */srv/www/htdocs* or */srv/www/html*. Go to that directory:
  ```
  cd /srv/www/htdocs
  or 
  cd /var/www/html
  ```
* Transfer the file
  *ricgraph-research-in-context-graph-files.tar*
  from this GitHub repository
  to your web server, by typing on your webserver
  in that directory: 
  ```
  wget https://github.com/UtrechtUniversity/ricgraph-website/raw/main/ricgraph-website/ricgraph-research-in-context-graph-files.tar
  ```
* If directory *ricgragh-website* already exists, remove
  all files in it, and continue with the next step.
  
  If it does not exist, create it:
  ```
  mkdir ricgraph-website
  ```
* Go to it:
  ```
  cd ricgraph-website
  ```
* Extract the files in this directory using tar:
  ```
  tar xf ../ricgraph-research-in-context-graph-files.tar
  ```
* Change the owner of all files you have just extracted and
  make sure the Linux permissions are correct:
  ```
  cd ..
  chown -R root:root ricgraph-website
  chmod -R g-w ricgraph-website
  chmod -R o-w ricgraph-website
  ```
* Make sure your web server configuration file has been configured correctly.
* Restart your web server.
* Check if the website is working correctly.
* Exit from user *root*.
* Done.
