# colab-content-backup-and-recover

# About
Backup and Recover (BARE): "Due to the time limit of Google Colaboratory, your folder project structure, including your saved progress, will be deleted after the runtime ends. Why don't you back up the entire contents of your project, including its current states, by simply running the **Backup Cell** and the **Recover Cell**, so that you can access it at any time with its previous state".

# How it works?
* It will create directory based on `BARE_DIRECTORY` environment variable in secret Google Colaboratory feature. If it's not set, it will create default directory so your MyDrive will looks like `MyDrive/bare-colab-contents/`. Setting this environment will be good idea for colaborating with other colaborators with *Add to Shortcut* to *My Drive*.
* The directory will be used to store compressed contents in zip format.
* The compression is protected by password that based on `BARE_KEY` environment variable in secret Google Colaboratory feature. If it's not set, it will use default password.
* To backup, simply run the **Backup** cell. It will zipping entire `/content` and store it to the `BARE_DIRECTORY`. Backup requires mount permission.
* To recover, simply input public **DRIVE_ID** which means the zipped content file or **BARE_DIRECTORY** must be set to **VIEWER** then run **Recover** cell. Restore doesn't require mount permission.
* To list available **DRIVE_ID**, you can simply run **List Available Contents** cell. But, it requires mount permission. If you don't want to mount the runtime, you can **manually** inspect the **DRIVE_ID** in **BARE_DIRECTORY**.
