# Preparing to Make the Server
This is assuming you have administraitive rights on your computer, and that you have a basic understanding of how to navigate Windows and have Steam with Arma 2 and Arma 2: Operation Arrowhead in your library.
You will want to restart after finishing these.
## Downloads
* Download and install Arma 2 and Arma 2 Operation Arrowhead. After installing go ahead and click Verify Integrity of Files. Run Arma 2 until the main menu, then close it, and run OA till main menu then close it.

* Download and install the [DayZ Launcher](http://app.dayzlauncher.com/updates/setup_dzlauncher.exe), Open it and go to Settings -> Mod Path -> Set it to your Arma2:OA steam directory, should look something like this "steamapps\common\Arma 2 Operation Arrowhead''. Set the Arma 2 path to your Arma 2 directory, should look something like this "steamapps\common\Arma 2". Now go out of the settings, click at the top on "Mods", download and install "DayZ Epoch 1.0.7". Verify it after if needed.

* Download Epoch [Server Files](https://drive.google.com/file/d/1jDn86sfTwcRae4NZgHK76k_CaY1jOUP2/view) for 1.0.7 

* Downloading and installing MySQL, You can download the newest [version here](https://dev.mysql.com/downloads/windows/installer/8.0.html) or you can install [MySQL 5.7](https://dev.mysql.com/get/Downloads/MySQLInstaller/mysql-installer-community-5.7.36.1.msi) like the old days. Configuring 5.7: Server Only, Standalone, Server Machine. Root password is important, make it good!. C:/ -> ProgramData -> MySQL -> MySQL Server 5.7 -> 'my.ini' right click and edit. Find Line 75 or 76:'[mysqld]', Right BELOW it, add "event_scheduler = ON", save.Open windows Services -> find MySQL 5.7 -> Restart it.

* Download and install [HeidiSQL](https://www.heidisql.com/download.php?download=installer) 

* Download and install [PBO Manager](https://drive.google.com/file/d/1V_ivuaVIkDJuqULvhwAfbEtlp45eOE-X/view?usp=sharing), to make sure your PBO Manager was installed correctly go to Windows Settings -> type "defaults" -> Default Apps -> Choose default apps by file type -> Scroll down to '.pbo' on the left and make sure PBO Manager is the application assigned to it. You should see the  icon next to PBO files now.

* Download and install [WinRAR](https://www.win-rar.com/fileadmin/winrar-versions/winrar/th/winrar-x64-602.exe) or [7 Zip](https://www.7-zip.org/a/7z2106-x64.exe)

* Download and install [Visual Studio Code](https://code.visualstudio.com/docs/?dv=win) and [Notepad++](https://github.com/notepad-plus-plus/notepad-plus-plus/releases/download/v8.1.9.3/npp.8.1.9.3.Installer.x64.exe) we will be using both!

*Download the [Setup Guide Files folder](https://drive.google.com/drive/folders/1ln5BWdNLfw1AcWfyHHCORErb2O-bQwIo) (Start.bat ect) from the google drive to follow along with.
## Misc
* Open your Network Configuration in your browser: We need to Port Forward 2302-2307; [How To Port Foward](https://www.hellotech.com/guide/for/how-to-port-forward), it's only necessary if you are planning on hosting from this machine, as some people may only want a test server. Remember you need to forward the ports for both TCP and UDP.

* Search in Windows "Add or Remove Programs" -> Apps & Features -> Scroll down and look for Visual Studio C++ Redistributables 2008-2015 both x64 and x86, if you don't have them, install them. [Redistributables](https://docs.microsoft.com/en-US/cpp/windows/latest-supported-vc-redist?view=msvc-170), start from the earliest and work your way to the newest, x64.  

## Done
You should now have all the files required to setup the server, we are ready to set them up and start the server, please click below to return to the ReadMe.

[Click Here to Continue](../main/README.md)
