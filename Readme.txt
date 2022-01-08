Please read everything slowly and step by step

#### Multi-User Method #### ( Recommeneded for beginners )

After a fresh install and swupd has finished updating…
Add new user to admin group

    sudo useradd enlightenment -g wheel

Set password for new user enlightenment

    sudo passwd enlightenment

Install enlightenment bundle

    sudo swupd bundle-add desktop-enlightenment

Install example_theme.tar

    sudo tar -xf example_theme.tar -C /home/enlightenment/
    sudo mv /home/enlightenment/example_theme /home/enlightenment/.e
    sudo chown -R enlightenment /home/enlightenment/

Now use the Switch User... Option at the top right menu
Before you type in your password, select the bottom right icon and select the Enlightenment Desktop.

#### Extra Optional Stuff
New user can add flatpak repo with:

    flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo

Once you’ve test the theme you can override passwd for quicker logins ;-)

    sudo passwd -d enlightenment

Change hostname to something fancy ** Requires Reboot **

    sudo hostnamectl set-hostname fancypants

#### Single-User Method ####

If you don’t have a password make sure you set one up…

    sudo passwd $(whoami)

Install enlightenment bundle

    sudo swupd bundle-add desktop-enlightenment

Extract the example_theme.tar with the following
DO NOT USE SUDO…

    tar -xf example_theme.tar -C $HOME/
    mv $HOME/example_theme $HOME/.e

Log out and change the display manager as you would with switching users by selecting the lower right icon, and select enlightenment.

If you have accidentally used sudo to extract the theme for single user method, open up a tty3 session <alt+ctrl+F3>, log in and reboot.

    sudo reboot

Once rebooted, select Gnome Xorg as display manager and login, then open up terminal and type:

    sudo chown -Rv $(whoami) /home/$(whoami)/.e

Open up File Manager (nautilus) and select show hidden files and delete the folder “.e” with the file manager. Then extract the example_theme again without using sudo and follow the steps again.
