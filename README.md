# apache-server-statistic
Bash script for Zabbix-agent on remote host
# How to Use

   0. Place script wherever in accessible directory
      for Zabbix user(i.e. **'/etc/zabbix/scripts'**)
      on the remote Apache server with working zabbix agent
   1. Configure paths for variables (if necessary)
      (by default script ueses default directory for openvpn logs)
   2. Grant access for Zabbix user to script directory
      and script itself
      
      > chown root:zabbix -R /etc/zabbix/scripts
      
      > chmod 550 /etc/zabbix/scripts/apache_server_statistic.sh
      
   3. Add UserParameter in zabbix_agent.conf (you can place it as well after "UnsafeUserParameters")
      
      > UserParameter=apache2[*],/etc/zabbix/scripts/apache_server_statistic.sh "none" "$1" "$2"
         
   4. Restart the Zabbix agent (according to your installation)
      
      > systemctl restart zabbix-agent
       
   5. Import **template-apache-statistic.xml**
   6. Enjoy!