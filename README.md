# DO288 Practice Exam
## Key Information
1. Remember to use a text editor that doesn't mess up POSIX line endings, which means under no circumstances should you ever use Windows Notepad. VIM, Notetab, Notepad++, Sublime, Gedit, Atom, VSCode, or literally any other text proper editor should work fine. Windows Notepad WILL break configurations.
2. Capitilization in naming matters. Spell all required components exactly as written or you will not recieve credit.
3. Your OpenShift project for both sections will be **_firstname-lastname_** on cluster <https://c103-e.us-south.containers.cloud.ibm.com:31712>.

---

## Prerequisite
You must create your exam project. Project must be in the format: 
**_firstname-lastname_** on cluster <https://c103-e.us-south.containers.cloud.ibm.com:31712>

---

## Exam Section 1 - Creating an Apache application from template
Criteria - Edit the provided template such that the application meets the following criteria:  
1. Application should be available via https at an exposed route in your assigned project.  
2. Pod should operate internally on port `8080`.  
3. Application should be named `exam-apache` with a TLS enabled route exposed at `https://exam-apache-YOURPROJECT.ose-internal-1602064171-f72ef11f3ab089a8c677044eb28292cd-0000.sjc03.containers.appdomain.cloud/` where YOURPROJECT is your assigned project name.  
4. Application should return the contents of [index.html](https://github.com/mclarkson78/example-apache/blob/master/index.html) and a `200 OK` http status when visited with `curl` or a standard web browser.  

Template location: <https://github.com/mclarkson78/example-apache/blob/master/openshift/templates/httpd.json>

---

## Exam Section 2 - S2I Build  
Criteria - Perform a S2I build using the following criteria and provided Git repository.  
1. Your resulting application should be named `sillywebsite`.  
2. Your resulting application should have an https route that should return the contents of [index.html](https://github.com/mclarkson78/example-website/blob/master/index.html) and a `200 OK` when visited with `curl` or a standard browser.
3. Route must be TLS encrypted and have an address of `https://sillywebsite-YOURPROJECT.ose-internal-1602064171-f72ef11f3ab089a8c677044eb28292cd-0000.sjc03.containers.appdomain.cloud/` where YOURPROJECT is your assigned project name.
3. Your application should use the httpd 2.4 builder image.  

Source repo location: <https://github.com/mclarkson78/example-website/> 

---

## Exam Section 3 - PHP Images with Access Control
The application image contains a PHP application that displays the web server environment and the PHP interpreter configuration. You should be able to deploy the application according to the following requirements:
1. The project that hosts the image stream for the image built outside of OpenShift should be named **_firstname-lastname_**-colorado.
2. The application project should be named **_firstname-lastname_**-texas.
3. Both the **_firstname-lastname_**-colorado and **_firstname-lastname_**-texas project should be owned by your user.
4. Grant pull access to pods from the **_firstname-lastname_**-texas project to image streams in the **_firstname-lastname_**-colorado project.
5. The Git repository that contains the source code and Dockerfile for the container image is: https://github.com/Joel-Adams/php-info.git. 
6. Build the container image and tag it as php-info. Push the tagged image to your quay.io registry. (create a new public repository named php-info if needed)
7. Add the newly created php-info image as an image stream to the OpenShift internal registry.
8. Deploy an application based on the php-info image.  The application name should be dallas and the application should be TLS encrypted and have an address of `https://dallas-YOURPROJECT.ose-internal-1602064171-f72ef11f3ab089a8c677044eb28292cd-0000.sjc03.containers.appdomain.cloud/` where YOURPROJECT is your assigned project name.

