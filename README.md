# nginx-to-git
Gitlab-CI which allows you to store/modify configs from the git. Also, if there are uncommitted changes, a notification is sent to the telegram. Supports forced synchronization of configs with git.

Variables:
- KEYPASS - passphrase for ssh key
- SSH_KEY - private key in base64
- SSH_USER - user on whose behalf the login occurs
- TG_BOT_TOKEN - telegram bot token
- TG_CHAT_ID - id of tg chat

Variables for scheduled pipelines:
Repository Sync:
   - Interval Pattern: Custom ( 0 0 * * * )
   - Cron Timezone: Moscow
   - Target Branch: master
   - Variables: CRON_SYNC: yes

Check uncommited changes:
   - Interval Pattern: Custom ( 0 9-19 * * 1-5 )
   - Cron Timezone: Moscow
   - Target Branch: master
   - Variables: CRON_CHECK: yes
