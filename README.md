# init.d

copy ark-server to /etc/init.d and make it executeable
chmod +x /etc/init.d/arc-server

edit /etc/init.d/arc-server and set your script folder and backup directory and your start script
for rcon msg function rcon need to be enabled

compile rcon.c to your script folder (for example /home/steam/scripts/)
gcc -o rcon rcon.c
copy msg.sh and update.sh to you script folder

edit update.sh and change your install directory
edit msg.sh and edit your rcon credentials (rcon need to be enabled via start options for arc or in GameUserSettings.ini)

example cron jobs

0 4 * * * /etc/init.d/ark-server backup
50 4 * * * /home/steam/scripts/msg.sh "Der Server wird in 10 minute fuer die taegliche Wartung heruntergefahren. Es kann einige Minuten dauern bis der Server wieder erreichbar ist."
0 5 * * * /etc/init.d/ark-server update
