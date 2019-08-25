---
layout: post
title: "MySQL for when I forget the root password"
date: 2019-07-18
--- 

I have forgotten the root password for MySQL often enough that I have looked up these commands more than once. 

**Starting, stoping, and restarting**
<pre><code>sudo /usr/local/mysql/support-files/mysql.server start
		sudo /usr/local/mysql/support-files/mysql.server stop
		sudo /usr/local/mysql/support-files/mysql.server restart</code></pre>
**Start without a password**
<pre><code>sudo mysqld_safe --skip-grant-tables &</code></pre>
**Connect**
<pre><code>mysql -uroot</code></pre>
**Set new password**
<pre><code>use mysql;
		
		
		UPDATE mysql.user SET authentication_string='password' WHERE User='root'; 
		
		flush privileges;
		
		quit</code></pre>

<p>Stop and start MySQL and viola.</p>
