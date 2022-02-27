**1. Hide the user**

First make the `user` a system user, so it will get hidden from login screen.

`$ cd /var/lib/AccountsService/users/
  $ sudo vim user.conf`

**2. Here user is the name of the user you want to hide. Now, change following:**

`SystemAccount=false` // for not hiding

To:

`SystemAccount=true` // for hiding


So, you hide your user. Now How will you login? For that you need a manual login method.

**2. Add manual login option**

` $ sudo vim /usr/share/lightdm/lightdm.conf.d/50-<distro name>.conf`

2. add the following line at last,

`greeter-show-manual-login=true`

Done.

Now you can reboot the system. You will see there is no login for `$USER`. Although there will be an option to login manually using username and password. Go for it! 