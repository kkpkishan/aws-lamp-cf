# AWS LAMP Templates
<table width="100%">
    <tr>
        <th align="left" colspan="2"><h4><a href="https://github.com/kkpkishan/aws-lamp-cf.git"> LAMP</a></h4></th>
    </tr>
    <tr>
        <td width="100%" valign="top">
           <p>Creates an entire LAMP from scratch for Lab or Permanent.</p>
           <h6>Install a LAMP web server on the Amazon Linux AMI</h6>
           <ol>
            <p>The following procedures help you install an Apache web server with PHP and MySQL support on your Amazon Linux instance (sometimes called a LAMP web server or LAMP stack). You can use this server to host a static website or deploy a dynamic PHP application that reads and writes information to a database.</p>
            <tr>
                      <td nowrap  valign="top">
            <table>
                <tr>
                    <th align="left">Launch</th>
                </tr>
                <tr>
                    <td>
                        <p>Alert</p>
                        <a href="https://console.aws.amazon.com/cloudformation/home?#/stacks/new?&templateURL=https://raw.githubusercontent.com/kkpkishan/AWS-SNS/master/alert.yaml" target="_blank"><img src="https://s3.amazonaws.com/cloudformation-examples/cloudformation-launch-stack.png"></a>
                    </td>
                    <td>
                        <p>EC2 Subnet LAMP</p>
                        <a href="https://console.aws.amazon.com/cloudformation/home?#/stacks/new?&templateURL=https://raw.githubusercontent.com/kkpkishan/aws-lamp-cf/main/public-lamp-instance.yaml" target="_blank"><img src="https://s3.amazonaws.com/cloudformation-examples/cloudformation-launch-stack.png"></a>
                    </td>
                </tr>
            </table>
        </td>
    </tr> 
    </ol>
 </table>

## Additional Configuration for VSFTPD
If you enable VSFTPD and have a public IP address enabled, it is necessary to update the public IP address in the VSFTPD configuration file. Please follow these steps:

1. Open the VSFTPD configuration file:
   ```bash
   sudo nano /etc/vsftpd/vsftpd.conf
   ```
2. Add the following line to the end of the file, replacing `xx.xx.xx.xx` with your actual public IP address:
   ```bash
   pasv_address=xx.xx.xx.xx
   ```
3. Save the file and exit the editor.
4. Restart the VSFTPD service to apply the changes:
   ```bash
   sudo systemctl restart vsftpd.service
   ```
