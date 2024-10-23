# kali-macbook-wifi
For people running Kali on a 2012 MacBook Pro who can't get wifi to work.


I was inspired by my professor to revive my old 2012 MacBook Pro and use it to run Kali. The install worked fine but for some reason the drivers for the Broadcom wifi card weren't initialized correctly.

I was able to find the driver online and install it manually but I needed to run two commands in order to get it to work. I would need to do this every time I rebooted the machine.

If you are encountering this issue as well, here are some detailed instructions on how to set up your system so that the wifi card is initialized correctly.

Step 1: Follow normal instructions for specfic model of MacBook you have.

Google the issue, find the device driver that should've been installed and install it manually.
(For me, I needed to install a Broadcom driver)

Step 2: Download the shell script and run it. (ex: ./wifi.sh)

You might need to run it as root. (ex: sudo ./wifi.sh) 

You should see the wifi symbol appear and the service should start to work. If not, you might need to continue to google the issue. Hang in there!

Step 3: Make sure script can be executed.

Can be done using chmod. (ex: chmod +x /wifi/sh)

Just make sure the file can be executed by all users for the next step.

Step 4: Use crontab (cron) to execute file on startup.

Type (crontab -e) into terminal. (If it isn't installed, install it by following the prompts)

Select an editor. (I use nano).

Go to the end of the file and enter (@reboot  <path to file>). (ex: @reboot  /home/user/Desktop/wifi.sh)

Save the file.

Reboot.

Your wifi should be enabled every time you reboot your computer from now on.
