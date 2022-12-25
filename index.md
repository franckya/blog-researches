# Welcome to Yannick Djomo blog!

You are all welcome to connect with me and contribute to my researches.

You can use the [editor](https://github.com/franckya/blog-researches/edit/gh-pages/index.md) to maintain and preview the content of my website in Markdown files.

### Opennms for Monitoring

System Requirements: 

- Java 11: OpenNMS Horizon 29 runs on JDK 11.

- PostgreSQL 10 or higher: Horizon 29 requires any supported version of PostgreSQL from 10 up to (and including) 14.

Note: If you are upgrading from a version of OpenNMS Horizon older than 29, you will have to fix the ownership of your files.

#### Fixing Permissions and Ownership

Java ICMP Permissions

- OpenNMS will attempt to configure ICMP permissions using the net.ipv4.ping_group_range sysctl. However, Linux kernels older than version 3.11 (like the version provided by CentOS 7) do not support this setting fully.

- If you are on a distribution with an older unsupported kernel, you can give Java ICMP permissions using the setcap utility once you have completed your upgrade. Note that this example assumes you have already run $OPENNMS_HOME/bin/install after install or upgrade, so

$OPENNMS_HOME/etc/java.conf exists.
setcap cap_net_raw+ep $(</opt/opennms/etc/java.conf) && echo "$(dirname $(</opt/opennms/etc/java.conf))/../lib/jli/" > /etc/ld.so.conf.d/java.conf && ldconfig -v

- Make sure to run as a root to avoid the 'permission denied' error

For more details see [What's New in OpenNMS Horizon 29](https://docs.opennms.com/horizon/29/releasenotes/whatsnew.html).


## If you are looking to install OpenNMS on CentOS 8, click [here](https://franckya.github.io/openNMS/) to access the code, and let us know if you are experiencing any issue. 

### Create an API Key on AWS

To create an API key on AWS (Amazon Web Services), you will need to use the AWS Identity and Access Management (IAM) service.

Here are the steps to create an API key:

1. Sign in to the AWS Management Console.

2. Navigate to the IAM service.

3. In the left-hand menu, click on "Users" and then click the "Add user" button.

4. Enter a user name for your new user and select the "Programmatic access" checkbox under "Access type".

5. Click the "Next: Permissions" button to move to the next step.

6. On the "Set permissions" page, you can either attach an existing policy directly to the user, or create a new policy using the JSON or visual editor.

7. After you have set the permissions for the user, click the "Next: Review" button to review the user details.

8. Click the "Create user" button to create the user and generate the API key.

On the final page, you will see the access key and secret access key for the user. Make sure to save these somewhere secure, as you will not be able to view the secret access key again.

That's it! You have now created an API key on AWS using the IAM service. You can use these keys to authenticate your API requests to AWS services.


### Yannick Djomo

For more information about this repository, visit or clone it at [blog-researches](https://github.com/franckya/blog-researches/settings/pages). 

### Support or Contact

Having trouble with Pages? [Book an Appointnment](https://calendly.com/fkengne-mcdns/30min?month=2022-03) with me to discuss more , and I we’ll help you sort it out.

March 2022 Blog
