# The general challenges are noted here

### Challenge) Even after using foxy proxy the designer is not loading.

Solution) exit chrome and run the following command in terminal 
```
open -a "/Applications/Google Chrome.app" --args --proxy-bypass-list="*.fa.ocs.oc-test.com;*.oraclecorp.com;*cls.ocp.oc-test.com;^((?\!static).)*.oracle.com" --proxy-server="http://www-proxy-idc.in.oracle.com" 
```
then input the username and password given when asked while opening designer page

---
