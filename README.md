# bank-config-server

We are adding webhook on github for refresh configurations at runtime using Spring Cloud Bus & Spring Cloud
Config Monitor. But for now we are working on localhost how can we add property link for webhook?
We are using this site(https://console.hookdeck.com/) for transforming localhost request to public link.

1- Add destination (Please follow the steps on site like me)

2- Copy Install with Scoop (scoop bucket add hookdeck https://github.com/hookdeck/scoop-hookdeck-cli.git)

3- Add above command your terminal. If the scoop command is not working on your windows machine, try the following steps.

  To install Scoop, you need to have PowerShell 5 or higher enabled on your machine. You can check your PowerShell version by running **$PSVersionTable.PSVersion** 
  in PowerShell.
  To install Scoop, you can follow these steps:
  Open PowerShell as a non-admin user and run this command to change the execution policy: **Set-ExecutionPolicy RemoteSigned -scope CurrentUser**
  Run this command to download and install Scoop: **iwr -useb get.scoop.sh | iex**
  Run **scoop help** to see the list of Scoop commands and options.

4- Run this on your terminal (**scoop bucket add hookdeck https://github.com/hookdeck/scoop-hookdeck-cli.git**) ,
  (**scoop install hookdeck**)

5- (**hookdeck login --cli-key 31w5ha3ujmpdf9huuauuaqv42q67uzso3jnbob1hj54psy3**)  

6- (hookdeck listen [port] Source)  --> (**hookdeck listen 8071 Source**)

7- If it is not asking for the forwarded path, pls run the this command,
  (**hookdeck listen 8071 source --cli-path /monitor**)
  When you are running the above command, you don't have to provide the hostname (localhost) specifically

8- Add created webhook url to github webhook settings
    source URL: https://hkdk.events/6p2dgi56ltfsyz


When you need new webhook session you can follow below steps.

1-  if you can not see the Add destination button clean your site caches before entered (https://console.hookdeck.com/)

2-  You need logout with your terminal. (**hookdeck logout**)

3- On site click -> Add Destination -> Localhost  skip to Step 2 because we did Step 1 before. Follow steps on site.

4- (**hookdeck login --cli-key 1s99ao5v4peq7ofu0x0nmnhbdzl08982aradfcby1h4hts**)

5- (hookdeck listen [port] Source)  --> (**hookdeck listen 8071 source --cli-path /monitor**)
    8071 our configserver port

6- Add created webhook url to github webhook settings
  Source URL: https://hkdk.events/h9azw5dmh78ilt




