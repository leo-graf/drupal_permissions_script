Drupal Permissions Script
=========================
##### Based on the documentation on https://www.drupal.org/node/244924

If you have sufficient privileges on your server:

* Place the file in `/usr/local/bin`    
* `sudo chown root:root /usr/local/bin/drupal-permissions.sh`    
* `sudo vi /etc/sudoers.d/drupal-permissions` and enter the following line in the file   
`user1, user2 ALL = (root) NOPASSWD: /usr/local/bin/drupal-permissions.sh`    
Note: Substitute your desired comma separated list of users where you see user1, user2 above. Alternatively, you could enter an ALIAS for a user list. Run man sudoers for more information on formatting the line.
* Save the file and then sudo chmod 0440 `/etc/sudoers.d/drupal-permissions`   


What the `/etc/sudoers.d/drupal-permissions` accomplishes is making the script available to a set of users via the sudo command without having to enter a password.

Run the script as follows:
`sudo bash fix-permissions.sh --drupal_path=your/drupal/path --drupal_user=your_user_name`

Note: The server group name is assumed "www-data", if it differs use the `--httpd_group=GROUP` argument.

