# Calendar2Dock
A date indicator for Plank that does absolutely no other job

```
cd ~/bin # it most probably exists
mkdir dcalendar
cd dcalendar
cp ~/Downloads/Calendar2Dock-main.zip .
unzip Calendar2Dock-main.zip
mv Calendar2Dock-main/dcalendar.tar.gz .
rm -r Calendar2Dock-main*
tar xvzf dcalendar.tar.gz
rm dcalendar.tar.gz
mv dcalendar/* .
rm -r dcalendar
chmod 755 Calendar2Dock.desktop.bak calendar2dock updateCalendar2Dock
cd ..
ln -s dcalendar/calendar2dock .
ln -s dcalendar/updateCalendar2Dock .
updateCalendar2Dock
```

Then the indicator should appear at the end of Plank right away.

For daily updates, run `crontab -e` and append to it the line 
`0 0 * * * bash $HOME/bin/updateCalendar2Dock` (You may need to
explicitly replace $HOME with your $HOME variable). Finally, 
restart the cron service:

```
sudo service cron restart
```

on openSUSE. On ubuntu-based distros, it may be `crond` or 
`cron.services` or `crond.services`.
