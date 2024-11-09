Here’s an extensive list of Google Dorks you can use for bug bounty hunting across various platforms, including common files, sensitive directories, configurations, and potential vulnerabilities.


Common File Extensions for Web Applications


###### 1. ASP (Active Server Pages)

filetype:asp

Useful for: Identifying ASP-based applications on Microsoft servers.

###### 2. ASPX (Active Server Pages Extended)

filetype:aspx

Useful for: Finding ASP.NET applications, which can often expose .NET-specific vulnerabilities.

###### 3. JSP (JavaServer Pages)

filetype:jsp

Useful for: Locating Java-based web applications running on platforms like Apache Tomcat.

###### 4. JSPX (JavaServer Pages XML)

filetype:jspx

Useful for: Identifying advanced Java applications with XML-based JSP pages.

###### 5. PHP (PHP Hypertext Preprocessor)

filetype:php

Useful for: Finding PHP-based applications; common for CMSs like WordPress, Joomla, and Drupal.

###### 6. DO (Action Servlet)

filetype:do

Useful for: Identifying Java applications using Struts or other Java-based frameworks that route actions via .do endpoints.

###### 7. CFM (ColdFusion Markup)

filetype:cfm

Useful for: Finding ColdFusion applications that might reveal database or configuration info.

###### 8. HTML (HyperText Markup Language)

filetype:html or filetype:htm

Useful for: Locating general web pages; works universally.

###### 9. SHTML (Server-Side Includes)

filetype:shtml

Useful for: Discovering SSI (Server Side Includes), often vulnerable to inclusion attacks.

###### 10. PL (Perl Script)

filetype:pl

Useful for: Identifying CGI scripts in Perl, common on older servers.

###### 11. CGI (Common Gateway Interface)

filetype:cgi

Useful for: Discovering older web applications running scripts.

###### 12. XML (eXtensible Markup Language)

filetype:xml

Useful for: Finding configuration or API files, which may expose sensitive information.

###### 13. JSON (JavaScript Object Notation)

filetype:json

Useful for: Identifying API responses, configurations, and sometimes credentials.

###### 14. YAML (YAML Ain't Markup Language)

filetype:yaml or filetype:yml

Useful for: Finding configurations, especially in DevOps environments.

###### 15. CONFIG (Configuration Files)

filetype:config

Useful for: Locating configuration files, which often contain database credentials or API keys.

###### 16. LOG (Log Files)

filetype:log

Useful for: Discovering log files, which can reveal error messages, paths, and sensitive info.

###### 17. TXT (Text Files)

filetype:txt

Useful for: Finding text files containing notes, backups, or configuration details.

###### 18. JS (JavaScript Files)

filetype:js

Useful for: Locating JavaScript files, which can expose API endpoints and client-side logic.

###### 19. SWF (Shockwave Flash)

filetype:swf

Useful for: Identifying Flash files, often outdated and vulnerable.

###### 20. EXE (Executable Files)

filetype:exe

Useful for: Finding downloadable executables; potential for malware or vulnerabilities.

###### 21. ZIP (Compressed Archive)

filetype:zip

Useful for: Discovering compressed archives, often backups or sensitive data.

###### 22. RAR (Roshal Archive)

filetype:rar

Useful for: Identifying RAR files that may contain sensitive information or backups.

###### 23. TAR and TAR.GZ (Unix Archive)

filetype:tar or filetype:tar.gz

Useful for: Finding Unix/Linux compressed backups or configurations.

###### 24. DOCX/DOC (Microsoft Word Document)

filetype:docx or filetype:doc

Useful for: Discovering Word documents containing notes, specifications, or credentials.

###### 25. XLSX/XLS (Microsoft Excel Spreadsheet)

filetype:xlsx or filetype:xls

Useful for: Finding spreadsheets, potentially containing sensitive or structured data.

###### 26. PPTX/PPT (Microsoft PowerPoint Presentation)

filetype:pptx or filetype:ppt

Useful for: Locating presentations, often containing insights into internal operations.

###### 27. SQL (Structured Query Language File)

filetype:sql

Useful for: Discovering database dumps, which may include full or partial databases.

###### 28. BAK (Backup File)

filetype:bak

Useful for: Finding backup files that could contain full copies of sensitive information.

###### 29. MDB (Microsoft Access Database)

filetype:mdb

Useful for: Locating Access databases, which might reveal tables and sensitive data.

###### 30. PS1 (PowerShell Script)

filetype:ps1

Useful for: Finding PowerShell scripts, which may include administrative or automation tasks.

###### 31. SH (Shell Script)

filetype:sh

Useful for: Discovering shell scripts, often containing automation or deployment commands.

###### 32. PY (Python Script)

filetype:py

Useful for: Locating Python scripts, which can reveal application logic and API integrations.

###### 33. RB (Ruby Script)

filetype:rb

Useful for: Identifying Ruby code files, often used in web applications and scripts.

###### 34. JAR (Java Archive)

filetype:jar

Useful for: Finding Java archives, which might contain entire application code.

###### 35. WAR (Web Application Archive)

filetype:war

Useful for: Discovering deployable Java web applications, which could reveal application behavior.

###### 36. DAT (Data File)

filetype:dat

Useful for: Identifying general-purpose data files, which may contain logs or configuration data.

###### 37. DB (Database Files)

filetype:db

Useful for: Locating database files in SQLite or other formats, which may include sensitive data.

###### Example Google Dork Queries Using File Extensions

site:example.com filetype:env

site:example.com filetype:bak

site:example.com filetype:php inurl:config

filetype:log "password" inurl:"/logs"

intitle:"index of" filetype:sql


# Always use these responsibly and ensure authorization from the site owner when using Google Dorks for testing.



###### 1. Finding Login Pages

inurl:login

inurl:signin

inurl:admin

inurl:dashboard

inurl:user/login

intitle:"login page"


###### 2. Locating Sensitive Files

filetype:env "DB_PASSWORD"

filetype:sql "INSERT INTO"

filetype:log password

filetype:bak inurl:"/admin"

filetype:txt inurl:"/config"

filetype:xml inurl:"/config"

inurl:backup

inurl:db_backup


###### 3. Exposing Configuration Files

filetype:xml inurl:"configuration.xml"

filetype:ini "smtp" "password"

filetype:json "api_key"

filetype:conf "password"

inurl:phpinfo.php

filetype:yaml password


###### 4. Discovering Error Messages

intext:"Warning: mysql_connect()"

intext:"Warning: mysqli_connect()"

intext:"Notice: Undefined index"

intext:"Fatal error"

intitle:"index of /" "Apache/2.2.3 (CentOS)"


###### 5. Exposing Backup Files

intitle:index.of "backup"

intitle:index.of "website backup"

filetype:zip inurl:"backup"

filetype:rar inurl:"backup"

filetype:tar.gz inurl:"backup"

inurl:/backup.zip

inurl:/backup.sql


###### 6. Finding Development and Test Environments

inurl:dev

inurl:test

inurl:staging

inurl:qa

inurl:demo

intitle:"index of /" "dev"

intitle:"index of /" "test"


###### 7. Discovering Exposed Directories

intitle:"index of /" "admin"

intitle:"index of /" "uploads"

intitle:"index of /" "files"

intitle:"index of /" "download"

intitle:"index of /" "conf"

intitle:"index of /" "private"


###### 8. Locating API Keys and Sensitive Information in Code Repositories

site:github.com "client_secret"

site:gitlab.com "client_id"

site:bitbucket.org "aws_access_key_id"

filetype:json "api_key"

filetype:json "access_token"


###### 9. Searching for Open Database Interfaces

inurl:phpmyadmin

inurl:phpPgAdmin

inurl:myadmin

intitle:"phpMyAdmin"

intitle:"phpPgAdmin"

inurl:"/dbadmin"


###### 10. Finding Exposed Logs

intitle:"index of /" "error.log"

filetype:log inurl:"/logs"

filetype:log "error"

filetype:log "login"

inurl:/logs/access.log


###### 11. Discovering Publicly Accessible Git and Version Control Directories

intitle:"index of /" ".git"

intitle:"index of /" ".svn"

intitle:"index of /" ".hg"

intitle:"index of /" ".bzr"

inurl:".git/config"

inurl:".svn/entries"


###### 12. Exposing Emails and Contact Information

intext:"email" inurl:contact

intext:"email" inurl:support

intext:"admin" inurl:contact

inurl:contact.php "email"

inurl:support.php "email"


###### 13. Uncovering Potentially Vulnerable WordPress Sites

inurl:wp-content

inurl:wp-login.php

inurl:wp-admin

inurl:wp-config.php

filetype:php inurl:wp-content


###### 14. Identifying Exposed API Endpoints

inurl:api

inurl:api/v1

inurl:rest

inurl:rest/v2

inurl:graphql

inurl:auth


###### 15. Detecting Open Directories for Sensitive Data

intitle:"index of" "password"

intitle:"index of" "credentials"

intitle:"index of" "confidential"

intitle:"index of" "secrets"

intitle:"index of" "private"


###### 16. Finding Exposed Cloud Storage Buckets

site:amazonaws.com filetype:xml

inurl:s3.amazonaws.com

site:googleapis.com

inurl:"cloudfront.net"

inurl:"digitaloceanspaces.com"


###### 17. Revealing Public Jira and Confluence Pages

inurl:/jira/

inurl:/browse/

inurl:/confluence/

intitle:"index of /" "jira"

intitle:"index of /" "confluence"


###### 18. Locating Old and Archived Versions of Sites

inurl:old

inurl:archive

inurl:bak

inurl:backup

inurl:oldsite

inurl:previous


###### 19. Searching for Public FTP Sites

inurl:ftp

inurl:ftp://username:password@

intitle:"index of /" "ftp"

intitle:"index of /" "pub"

intitle:"index of /" "uploads"


###### 20. Finding Code, Development, and Test Files

filetype:js inurl:config

filetype:json inurl:config

filetype:yaml inurl:config

filetype:js "client_secret"

filetype:properties inurl:config

21. Locating User and Admin Directories

intitle:"index of /" "users"

intitle:"index of /" "accounts"

inurl:/users

inurl:/accounts

inurl:/members

###### 22. Looking for Vulnerable Parameters in URLs

inurl:redirect=

inurl:return=

inurl:next=

inurl:url=

inurl:callback=


###### 23. Identifying Open Admin Panels

inurl:admin

inurl:cpanel

inurl:login.php

inurl:administrator

inurl:dashboard
