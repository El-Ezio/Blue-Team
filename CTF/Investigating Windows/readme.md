today we are going to do the "Investigating Windows" room on tryhackme,this could be teach us some good stuff and make you investigate through the process. <br>

As in the description of this room says,there is a infected windows machince and you need to look inside it to understans what hacker did.<br>

Lets dig in🪏 <br>

1) The first one no need to mention it,it can be ezly find out.<br>

2) to this better to check out old friend,"Event viewer" <br>

3) When you find the second answer,you can also find the date  of last login. <br>

4)To this you can search on the local users wndows or if you want to get better at powershell,run the command:

 ```bash
 Get-LocalGroupMember -Group "Administrators" 
 ```
Shows which users and groups have local administrator privilege.

