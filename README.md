# Project 7 - WordPress Pentesting

Time spent: **5** hours spent in total

> Objective: Find, analyze, recreate, and document **five vulnerabilities** affecting an old version of WordPress

## Pentesting Report

1. (Required) XSS Vulnerability
  - [X] Summary: Wordpress was vulnerable to stored XSS. An attacker can inject JavaScript in WordPress comments.
    - Vulnerability types: stored XSS
    - Tested in version: 4.2
    - Fixed in version: 4.3
  - [X] GIF Walkthrough: https://imgur.com/a/WQ08Y
  - [X] Steps to recreate: 
	1.) Go to your wordpress local 
	2.) Click on a post
	3.) When prompted to reply input the string <a title='x onmouseover=alert(unescape(/hello%20world/.source)) style=position:absolute;left:0;top:0;width:5000px;height:5000px  AAAAAAAAAAAA...[64 kb]..AAA'></a> 
  - [X] Affected source code: core Wordpress
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
1. (Required) XSS Vulnerability
  - [X] Summary:Wordpress was vulnerable to stored XSS. An attacker can inject JavaScript in WordPress comments. 
    - Vulnerability types:XSS
    - Tested in version: 4.2
    - Fixed in version: 4.3
  - [X] GIF Walkthrough: https://imgur.com/a/KuW2q
  - [X] Steps to recreate: 
	1.) Go to your wordpress local
	2.) Click on a post
	3.) In the box for comments or replies type in <script>alert('XSS');</script>
  - [X] Affected source code: core Wordpress
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)
1. (Required) User Enumeration Vulnerability
  - [X] Summary: A vulnerability occurs when brute forcing the password in terminal.
    - Vulnerability types: User Enumeration
    - Tested in version: 4.2
    - Fixed in version: 4.6
  - [X] GIF Walkthrough: https://imgur.com/a/wKWKC
  - [X] Steps to recreate: 
	1.) In your terminal type "wpscan --url http://wpdistillery.local --enumerate u" and hit enter
	2.) Then in your terminal type "wpscan --url http://wpdistillery.local --wordlist" '/root/Desktop/rockyou-75.txt --username admin
	3.) Hit enter
	4.) After running through the possibilies it finds the password
  - [X] Affected source code: core WordPress
    - [Link 1](https://core.trac.wordpress.org/browser/tags/version/src/source_file.php)

## Assets

List any additional assets, such as scripts or files

rockyou-75.txt

## Resources

- [WordPress Source Browser](https://core.trac.wordpress.org/browser/)
- [WordPress Developer Reference](https://developer.wordpress.org/reference/)

GIFs created with [LiceCap](http://www.cockos.com/licecap/).

## Notes

Describe any challenges encountered while doing the work

I encountered some difficulties trying to get the various things like Kali Linux and Licecap to work. 


## License

    Copyright [2017] [Kestrel Bridges]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
