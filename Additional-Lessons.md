

**Things i learnt while figuring all these out**
- A Practical Lesson on Dependencies: I also did a kind of full upgrade on my Linux here just to get the services and dependencies needed for this activity up to date. Steps include:

```
Sudo apt autoremove (Removes unnecessary packages).

Sudo apt update (updates the package list)…..took a while.)

Sudo apt list – upgradeable (Shows me what i need to update.)

Sudo apt upgrade
```


- There are two course of actions here; you can either use the sudo apt upgrade(for a normal upgrade which updates existing services and dependencies needed by the application without swapping them for the newest versions or sudo apt full upgrade which does that. The issue is the former is safer i.e the devil you know while the later will make you up to date but there’s a risk of loss of functionality due to entirely new dependencies. So I chose sudo apt upgrade.

- So golden question, What are dependencies; the long and short of it is they are what makes an application tick i.e if the application was a pot of stew they are the ingredients i.e salt, maggi, etc i the functionality and quality of the stew depends on them. So sudo apt upgrade gives you same ingredients new quality; high probability of maintaining or increasing the quality of your stew, sudo apt full upgrade changes the type of stew you’re cooking you might like it, or you might not but it's still stew.

- After the upgrade you can proceed to install your tool.
```

Sudo apt install the tool-name (in this case Nmap)



Nmap – version (shows you the version of nmap you installed.
```

**The above step is a little run up on how to update dependencies and download any tool on kali by the way.**

- Another quirk I encountered was the constant prompt when ever a service is being upgraded to give permission to update from postgresql 17 to 18; it taught me that if I had DBs hosted on servers on my kali then this question would be more critical as the version my servers depend on(dependencies?, you see) would be what I’ll default to. I don’t so I accepted the upgrade.

- When I was doing the upgrade my laptop slept and by default kali automatically paused it; so I had to learn how to continue a download when your kali sleeps cause unlike your normal windows GUI environment there’s no play or pause option for the download. Just simply use the following step to check status and continue your process;
```

Ps aux | grep apt (searches for app upgrade process, if apt is found amidst result then it’s valid)

Then if apt is still running bring terminal back by simply pressing enter and voila upgrade resumed.
```

Another thing I had to brush up was the basics of IP addresses in relation to masks and subnets.

- Ip addresses are like house addresses; some part belongs to the street and others to the exact house you seek Masks help determine which exactly are these that belong to the network and which belongs to the computer  i.e 192.168.56.101. Normally Masks look like this 255.255.255.0. The Mask tells us that the first  three blocks(Octets) belong to the network and the last belongs to the computer i.e for example even though kali and windows vms have ; 101 and 102 as their final house numbers; they are in the same subnet mask i.e 192.168.56(255.255.255.0) and the implication of that is they don’t need a router to speak they can communicate directly, if they were on different subnets then they would  need a router to resolve addresses. Kindly check more resources for in depth explanation on subnetting and subnet masks.

- What is latency?; think of it as the distance and resistance a packet has to face traveling up and down a network i.e the higher the latency the slower the network and the lower the latency, the faster it is. Latency spikes are common indicators of a DDOS attack.

- A little lesson on SMBs i.e the SSH of Windows; So SMB(Service Message Blocks) are the protocols responsible for authentication on server, works closely with AD, key to file sharing and network mapping. They are important because of all these access they have to file paths and user profiles make them a lateral movement target by and attacker (lots of goodies there), not to mention compromise of password hashes. So SMB which uses port 445 by the way always has it’s traffic highly monitored. SMB v3 is the most secure as it is encrypted. SSH performs the same function for Linux on port 22 but it's less about file sharing but more about secure remote server access and authentication. 

Resources that helped with this project:
SUBNET MASKS EXPLAINED.
https://youtu.be/s_Ntt6eTn94?si=_bz4NCrhOL7j-pMs

HOW TO INSTALL WINDOWS 10 IN VIRTUALBOX VM:
https://youtu.be/CMGa6DsGIpc?si=qj44cExDj5T-uixF

ChatGpt.

Thank you for staying till the end.