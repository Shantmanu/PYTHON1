In actual development, when you receive a demand, for example, you need to do a "receive and send mail" function.

If you have no impression at all and no ideas, you can search directly on Google.

Because we cannot understand every point of knowledge, it is shameful not to understand, but we must know how to find information to understand.

To emphasize,

Search with Google.

Search with Google.

Search with Google.

IMHO, Baidu search is really spicy.

How do we find information?

First of all, we can directly Google "Python send and receive mail", we can get such a result.

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-10-15-065554.png)

This kind of commonly used demand, basically just look at the first few to know the general idea.

As you can see, the two modules smtplib and email are mainly used to implement mail sending and receiving with Python.


As for how to use these modules, see [Python official documentation](https://docs.python.org/3.7/library/smtplib.html?highlight=smtplib)

![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-10-15-065957.png)

Really, no tutorial is more complete than the official documentation.

But we can summarize these contents.

**1, SMTP sending mail**

The main steps of Python sending mail are as follows:

* `import smtplib` 
 -Import the `smtplib` module, which is mainly used to construct transmission services
* `server = smtplib.SMTP()`
 -SMTP is a class in the smtplib module. Instantiate this class so that we can call the methods in it.
 -SMTP (Simple Mail Transfer Protocol) translates to "Simple Mail Transfer Protocol". The SMTP protocol is a set of rules for transferring mail from a source server to a destination server.
* `server.connect(host, port)`
 -Connect to the specified server
 -host is the designated mailbox server for connection, you can specify the domain name of the server.
 -port port number of the server
 -How to find these, like qq mailbox, there are related switches and instructions in "Settings".
 -![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-10-15-090427.png)
 -Click the relevant description, you can see the corresponding server address and port number
 -![](http://twowaterimage.oss-cn-beijing.aliyuncs.com/2019-10-15-090619.png)
* `server.login(username, password)`
 -Login account password 
* `server.sendmail(from_addr, to_addr, msg)`
-Sending emails. Generally, who sent the emails to whom and what was sent? Summarized as three parameters, sender, receiver, and the content of the sent mail.
 -from_addr: mail sending address
 -to_addr: mail recipient address
-msg: The content of the sent email, the email content needs to use the `email` module. Through the `email` module we can define the subject, recipient information, sender information and so on.
* `server.quit()`
 -Exit service

 Just look at the example and send an email to the QQ mailbox:
 
 

