# Edoc-doctor-appointment-system v1.0.1  was discovered to cross-site request forgery (CSRF) vulnerability via /patient/settings.php . Allow remote attackers to hijack the authentication of users for requests that cause an unspecified impact via unknown parameters.

vendor : https://github.com/HashenUdara/edoc-doctor-appointment-system

Vulnerability Position : http://ip/patient/settings.php 



Log in to the http://ip/login.php

Visit http://ip/patient/settings.php  ,  will access the page of the module.



Click the View button.

![image-20220718153048821](.\img\image-20220718153048821.png)



Change name : `qq ww`  to  `hackhack`.

Use burpsuite to capture request packet , and then click the Save button.

![image-20220718153650026](.\img\image-20220718153650026.png)



Generate CSRF PoC in burpsuite.



![image-20220718153756018](.\img\image-20220718153756018.png)



Copy HTML save as test.html.

![image-20220718154658799](.\img\image-20220718154658799.png)



**Attention :** **You must drop this captured request packet after Copy HTML**.



Then open test.html with your Browser , click Submit request button.

![image-20220718155255767](.\img\image-20220718155255767.png)



You will see pop -up window , and your name is `hackhack`

![image-20220718155607311](D:\Pyproject\cve\bug_e\edoc-doctor-appointment-system\img\image-20220718155607311.png)

