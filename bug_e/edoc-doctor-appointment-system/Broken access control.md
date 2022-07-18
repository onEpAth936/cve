# Edoc-doctor-appointment-system v1.0.1  was discovered to broken access control vulnerability. Allow remote attackers to edit , read ,delete Administrator data 

vendor:https://github.com/HashenUdara/edoc-doctor-appointment-system

Vulnerability Position：http://ip/admin/*



Log in to the http://ip/login.php as common user , and then copy common user's cookie.

```
PHPSESSID=ij53rgs126242sgjlc41oi449u
```

![image-20220718170731651](./img/image-20220718170731651.png)



Log out common user , and log in to the http://ip/login.php as administrator (email : admin@edoc.com , password : 123).



At this time , administrator's cookie is `PHPSESSID=nchpql9v6mnece6232ur7akjdi`.

![image-20220718171517897](./img/image-20220718171517897.png)



## Try to edit some data

Click Edit button , and change Doctor name to `Test Doctor hackhack`.

![image-20220718171858934](./img/image-20220718171858934.png)





Use burpsuite to capture request packet , and then click the Save button.

![image-20220718172337411](./img/image-20220718172337411.png)



Use common user's cookie instead administrator's cookie , requestion will redirect to someway.

Then click Follow redirection button.

![image-20220718173002849](./img/image-20220718173002849.png)

You will see success page , and `Test Doctor` change to `Test Doctor hackhack`.

![image-20220718173248849](./img/image-20220718173248849.png)





## Try to delete some data

Similar to edit data , you just click `Remove` button , then use burp suite to capture request packet , and then click the  `Yes` button.

![image-20220718173755117](./img/image-20220718173755117.png)



Use common user's cookie instead administrator's cookie , requestion will redirect to someway.

Then click Follow redirection button.

![image-20220718174054250](./img/image-20220718174054250.png)



You will see  `Test Doctor hackhack` information has gone.

![image-20220718174157323](./img/image-20220718174157323.png)