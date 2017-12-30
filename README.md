# Description
Steps to set-up WSL on your machine with some tips if something will doesn't work

## Step by step
1. Open "Turn Windows features on or off" (type this in Cortana/search bar) and check "Windows Subsystem for Linux" on the bottom of list. Your computer will be restarted and will be install some stuff. 
2. Open "Microsoft Store" and type "ubuntu" or "suse" in the search bar. You should get high header with title "C:\> Linux on Windows? Totally.", click the button "Get the apps" or choose one from "Apps" panel.
3. Install your choosed distro.
4. Run distro through app icon, or type "bash" in your powershell or cmd
5. Set up your linux user account and done!
5.1 Update all dependecies and libraries, type "sudo apt-get install && sudo apt-get upgrade"

## I have a error!
- You installed an apache2 and you got a "APR_TCP_DEFER_ACCEPT" error? Change a port in **/etc/apache2/ports.conf** on ie. 1000 and restart service. Still you got a error but your apache server works fine? Add "AcceptFilter http none" to end **/etc/apache2/apache2.conf**
- Your linux opening up but doesn't work? Change your pagefile(bing it) on one disk and restart a computer

## Questions
- How I can get access to my server on linux through PC or smartphone browser? Type: 
{your local IP or localhost(work only on PC)}:{port}/{path to folder in **/var/www/html**}
For example: http://192.168.1.2:1000/hello-wsl
- Can Linux get acces to files from Windows? Yes! Windows files are in **/mnt/{disk label}**, for example /mnt/c
- Can I link my htdocs folder from Windows to /var/www/html/ at Linux? Yes! Type
**ln -s "/mnt/c/xampp/htdocs" /var/www/html**, but watch out, you have to type than /htdocs/{folder name in your htdocs directory} to your URL, for example http://192.168.1.2:1000/htdocs/hello-wsl, or change behaviour by making htaccess file
- I develop app with NodeJS, I have to worry about port? No, if you change port on something else then 80

## Some resources
- https://github.com/Microsoft/WSL/issues/849#issuecomment-252053937
- https://docs.microsoft.com/en-us/windows/wsl/faq
- https://github.com/Microsoft/WSL/issues/1953
