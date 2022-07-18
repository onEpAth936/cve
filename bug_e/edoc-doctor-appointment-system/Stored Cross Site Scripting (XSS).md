# Stored Cross Site Scripting (XSS) vulnerability exists in edoc-doctor-appointment-system v1.0.1. A successful exploit could allow the attacker to execute arbitrary script code which could lead to stealing or modifying of authentication information of the user, such as data relating to his or her current session.

vendor : https://github.com/HashenUdara/edoc-doctor-appointment-system

Vulnerability Position : http://ip/patient/settings.php 



Log in to the http://ip/login.php

Visit http://ip/patient/settings.php  ,  will access the page of the module.



Click Account Setting.

![image-20220718134336627](.\img\image-20220718134336627.png)

And then insert `<script>alert(1)</script>` at the name box.

![image-20220718135038632](.\img\image-20220718135038632.png)

At last click the save button.

When you click View Account Details button , you will see the pop -up window.



![image-20220718135257659](.\img\image-20220718135257659.png)

![image-20220718135431746](.\img\image-20220718135431746.png)