# nagios-plugin-check_openvpn_status

Nagios plugin to check OpenVPN user status.

This is very similar to other OpenVPN plugins that use the OpenVPN management server, but doesn't require
use of a password passed into the plugin as a parameter, which improved security.


## Dependencies

* Perl 5
* Getopt::Long Perl module (Usually shipped with Perl)
* DateTime Perl Module
* Nagios::Plugin Perl Module (Usually shipped in one of your package manager's packages)
* * Debian/Ubuntu: `libnagios-plugin-perl`
* * Redhat/CentOS/Fedora: `perl-Nagios-Plugin`


## Installation

* Copy the `check_openvpn_status` to your nagios plugin folder and set executable.

* Add the following to your NRPE config (Plus any required options - See examples section below)
```
command[check_openvpn_status]=sudo /usr/lib/nagios/plugins/check_openvpn_status
```


## Examples

* Run with the --help argument to see all options
```
check_openvpn_status -h
```

* Specify maximum warning and critical values
```
check_openvpn_status -W 5 -C 10
```

* Specify minimum warning and critical values
```
check_openvpn_status -w 5 -c 3
```

* Specify custom OpenVPN status file
```
check_openvpn_status -f /path/to/openvpn-status.log
```

* Specify list of common names to require to be connected - Useful when providing site-to-site VPN connections
that should always be connected.
```
check_openvpn_status -N commonname1 -N commonname2
```


## Future Work

None planned


## Site

https://github.com/alasdairkeyes/nagios-plugin-check_openvpn_status


## Author

* Alasdair Keyes - https://akeyes.co.uk/


## License

Released under GPL V3 - See included license file.
