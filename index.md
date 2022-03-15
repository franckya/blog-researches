## Welcome to Yannick Djomo blog!

You are all welcome to connect with me and contribute to my researches.

You can use the [editor](https://github.com/franckya/blog-researches/edit/gh-pages/index.md) to maintain and preview the content of my website in Markdown files.

### What is new to Opennms?

System Requirements: 

- Java 11: OpenNMS Horizon 29 runs on JDK 11.

- PostgreSQL 10 or higher: Horizon 29 requires any supported version of PostgreSQL from 10 up to (and including) 14.

Note: If you are upgrading from a version of OpenNMS Horizon older than 29, you will have to fix the ownership of your files.

# Fixing Permissions and Ownership

Java ICMP Permissions

- OpenNMS will attempt to configure ICMP permissions using the net.ipv4.ping_group_range sysctl. However, Linux kernels older than version 3.11 (like the version provided by CentOS 7) do not support this setting fully.

- If you are on a distribution with an older unsupported kernel, you can give Java ICMP permissions using the setcap utility once you have completed your upgrade. Note that this example assumes you have already run $OPENNMS_HOME/bin/install after install or upgrade, so

$OPENNMS_HOME/etc/java.conf exists.
setcap cap_net_raw+ep $(</opt/opennms/etc/java.conf) && echo "$(dirname $(</opt/opennms/etc/java.conf))/../lib/jli/" > /etc/ld.so.conf.d/java.conf && ldconfig -v

- Make sure to run as a root to avoid the 'permission denied' error

For more details see [What's New in OpenNMS Horizon 29](https://docs.opennms.com/horizon/29/releasenotes/whatsnew.html).

### Yannick Djomo

For more information about this repository, visit or clone it at [blog-researches](https://github.com/franckya/blog-researches/settings/pages). 

### Support or Contact

Having trouble with Pages? book an appointment with me to discuss more [Book an Appointnment](https://calendly.com/fkengne-mcdns/30min?month=2022-03), and I we’ll help you sort it out.
