# This project is out of date and no longer supported

Please check out [Version 2.0 of my loader here](https://github.com/ThaisenPM/Cheat-Loader-CSGO-2.0)

# Nova Hook | Open Source VB.NET Cheat Loader


Hello! My name is Thaisen! I got bored so I started to build a basic cheat loader for whatever you need! The loader currently works off of MyBB for logging in, is HWID locked and validates the user's rank upon logging in. You can setup multiple ranks being allowed, blocking banned users from accessing the program and blocking users who do not fit the needed rank from accessing the program.

I recommend getting the font [Bebas Neue](http://www.dafont.com/bebas-neue.font) as it is just so clean, as well as it's the loader's default font.

The source in here is in no way refined, I spent 3-4 days on this, the first day being 100% dedicated to making the EXTREMELY basic "API" (Really just a database reader) for MyBB.

Although it comes pre-built for MyBB, you could easily update this to work with other forum softwares such as Xenforo. This loader can also be used for other games by going into the source and changing "csgo" to whatever process you want!

I will not be actively updating this project, but I may bring in some new features from time to time when I am bored and have nothing else to do. If you need support, first read the [FAQ](https://github.com/ThaisenPM/CheatLoader/blob/master/README.md#faq). If you still need help contact me on Discord at Thaisen#9999 or [on my Discord server](https://discord.gg/J8HNrPG)! (UPDATED 04/28/2019)

[Click here to download the source](https://github.com/ThaisenPM/CheatLoader/archive/master.zip). By downloading and using the source you agreed to the [License](#license) that comes with the loader.

Do you like what I'm doing with this repo? Wanna show me some love with one click? Why not click that "Star" button up above! It might keep me into this project and keep coming out with new versions for you guys to enjoy with new features you request, better security and overall cleaner code because it's a rats nest right now.

Please read the "known issues" section as it will give some insight to why your loader may not be working. I will try to update it with new information as they become known.

Have some code you wanna add to the repo? Let me know through an email (thaisenbusiness@gmail.com) and I will test it out and add you some credits and maybe let you collab on the repo.

## Contents
- Pre-Setup
    * [Screenshots](#screenshots)

    * [Requirements](#requirements)

- Setup
    * [SQL Setup](#sql)

    * [Web Files](#web)

    * [Web Setup](#web-files)

    * [Loader Setup](#loader-vb)

    * [Updater Setup](#updater-vb)
    
- Post-Setup
    * [Use Instructions](#use-instructions)

    * [Known Issues](#known-issues)

    * [License](#license)

    * [FAQ](#faq)

    * [Credits](#credits)

    * [Possible Updates](#possible-updates)

## Screenshots

<p align="center">
 <img src="https://i.gyazo.com/718c41797d1fa2171bec3f4a9dd9dd7f.png">
</p>

<p align="center">
 <img src="https://i.gyazo.com/b253471936f2681fc54e4c17f478d26a.png">
</p>

<p align="center">
 <img src="https://i.gyazo.com/3c63fa098965ec581d9091c66dbedcf1.png">
</p>

<p align="center">
 <img src="https://i.gyazo.com/7562a30bb5e04da0782b77507c05d0d6.png">
</p>

<p align="center">
 <img src="https://i.gyazo.com/24e7c1aa8d90ddff11827448d3fa67ec.png">
</p>

## Requirements

- A MyBB forum

- An undetected cheat

- Some SUPER BASIC knowledge of PHP and SQL

- Some decent knowledge of VB.NET

## SQL

1. Enter your PHPMyAdmin (Or whatever tool you use for SQL managment) and navigate to your mybb_users.

2. Click on the "Structure" tab at the top of PHPMyAdmin.

3. Now add a new column named "hwid" that is a "varchar" with a max limit of "255"

## Web

Upload the following files to your webserver:

- changes.txt

- hwid.php

- hwid_get.php

- status.txt

- usercheck.php

- usercheck_get.php

- version.txt

**OPTIONAL:**

- add a .dll of a cheat to your web server. Re-name it to ayyware.dll and put it into the root of your website (public_html/ayyware.dll)

## Web Files

1. Now navigate to the "hwid_get.php" and "usercheck_get.php" files on your website.

2. At the top of the files are "$link" and "$database".

3. Modify them to work for your website's setup.
    * The checks currently use forums_users, the default install of MyBB will make it mybb_users. Please make sure that they coincide correctly.
    * $link refers to your MySQL login... **NOT** your cPanel login... didn't think I'd have to put that in here

4. Go to your MyBB admin panel -> configuration -> general configuration.

5. Set the CAPTCHA field to none.

6. Now to go configuration -> login and registration options

7. Set "Number of times to allow failed logins" to 0

## Loader VB

**Goto Form1.vb**

1. Change the links from lines 18-20 to match your website.

2. Change "yoursite.com" on line 33 to your actual domain.

3. Change the link on line 65 to match your website.

4. Change the folder paths on like 82-89 to whatever you want them to be.

5. The lines commented from 92-111 check if the loader is on a USB and if steam is open or not. Uncomment if you want those features.

6. Change the domains on the following lines: 203, 222, 223, 237, 238, 270-272, 280-282, 328.

7. Change the group numbers to match your website

8. If you want the automatic update function, uncomment out Timer2_tick's sub. PLEASE NOTE some users are experiencing issues where they cannot get out of an auto update loop. I am too lazy to fix this issue, I was given code but I did not have the issue myself to start so I could not confirm if it was a fix or not. If you are stuck in an update loop, just take 15 minutes and try and fix it instead of spamming my Discord server, snapchat and steam.

**Goto Form2.vb**

1. Change localhost to your domain

**Goto Form3.vb**

1. Change any instance of "localhost" with your domain.

2. Add or remove whatever cheats you want to support (Currently lines 24-28 BUT is not limited to only 5)

**Goto Form5.vb**

1. Change lines 103-118 to match your setup for what cheats you wish to support

**Build your loader now, take it and rename it to "loader.exe" and upload it to your website.**

## Updater VB

1. On line 45, change the domain to your own.

2. Build your updater now, take it and rename it to "Updater.exe" and upload it to your website.

## Use Instructions

1. If you update the loader, change the version number in the loader's Form1.vb to the new number and change version.txt on your webserver

2. Change the folders from "C:\temp\Nova" to whatever you want. Do not leave them in this spot.

3. Status.txt on your webserver works like so. 0 = offline. 1 = online. 2 = maintenance.

4. For making an external cheat, these are your options.
    * Code the cheat in VB.NET and build it directly into the Loader
    * Make your cheat HWID locked and have it read "C:\temp\Nova\Nova.Hook.Username" and then use the information in the file and their HWID and have it enter the info into "yoursite/hwid.php" or 'yoursite/hwid_get.php?username=" + fileReader +"&hwid=" + hwid'
    * KEEP IN MIND! The cheat uses CPU, Mobo and MAC address then encrypts them with MD5.

5. If you do not want an external cheat, remove the label and adjust the other labels on Form3.vb under the groupbox named cheats.

6. To change where the cheat downloads from goto Form5.vb and edit the link on line 77.

**Congrats you can now sell your paste!**

## Known issues

1. Always getting "Password incorrect" while entering the correct password? Click the "Trouble Logging In? Click Here?" button and sign in and MAKE SURE you click "Remember me". Then click the button on the bottom left and try to sign in again.

2. If the domains don't change, go to the design tab. On Form1, expand the form size to be big. You will see 3 white boxes. The top right is the MyBB forum link, the bottom right is the usercheck.php and the bottom left is the hwid.php. Change those as well to be sure. Make sure to do the same thing on Form2 so that users experiencing the login failed issue can still get in to their account.

## License

This repo is listed with a [MIT license](https://github.com/ThaisenPM/Cheat-Loader/blob/master/LICENSE) which allows this to be used for commercial use, personal use and distribution and allows for modification of the source BUT does NOT allow me to be liable for what you do with the source and does not offer any warranty.

## FAQ

**Q: Is this a cheat for Counter Strike?**

A: No, this is a tool for being able to sell cheats without giving your .dll file to your users
___
**Q: Is this only for Counter Strike?**

A: No! Although it is targeted towards CS:GO it can literally be used for any game that takes dll based cheats
___
**Q: Is this detected by VAC?**

A: At the time of writing no. But make sure you change the signature of the loader to some extent.
___
**Q: If I am using this, do I have to give you credit?**

A: [The license for the project](https://github.com/ThaisenPM/Cheat-Loader/blob/master/LICENSE)
___
**Q: Can I use this for a massive P2C?**

A: Yes, but your stuff WILL get leaked eventually. I'd recommend using this for a private cheat for your friends with a max of like 30 members.
___
**Q: Do I need a website?**

A: Yes and no. You can make it local only by using a tool such as XAMPP but if you want it to be available for others to use you should get a website. Port forwarding would work too but I advise against it.
___
**Q: Why won't my cheat inject/why are the dlls downloading somewhere else/directory issues**

A: This is a common mistake. The cheat's dll filepath MUST have a trailing \ Meaning you type out the path that you want, then add a \ to the end. (Example of wrong: pszLibFileRemote = "C:\temp\Nova\dll" + filename :::: Example of right: pszLibFileRemote = "C:\temp\Nova\dll\" + filename). That MUST be there for both the injection of the .dll and for the downloading of the .dll.

**Q: How do I make paid usergroups on MyBB?**

A: https://community.mybb.com/thread-123597.html ALSO if you wanna be a real meme and need invite codes: https://community.mybb.com/thread-113141.html

## Credits

[JackkTutorials](https://www.youtube.com/channel/UC64x_rKHxY113KMWmprLBPA) for the [HWID creation and encryption code.](https://www.youtube.com/watch?v=CBe-gQiO-dA)

## Possible Updates

A few things I would possibly do, but don't get your hopes up.

To do:

- [ ] MyBB admin panel to change status and version
- [ ] Delayed injections

Completed:

- [X] Make dll's remove themselves automatically
- [X] Add a MOTD function (Kind of in the form of Change Logs)
- [X] Clean up login heavily
- [X] Auto-check user group after being logged in
