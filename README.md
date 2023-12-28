# Download Carbon Black Cloud Sensor via API and Install it. 

##   Written by Roshan Ratnayake @detectx.com.au
##
##   Purpose: 
##
##    Automatically download Carbon Black Cloud Sensor and install the sensor.
##
##   Usage;
##    
##     You will need to manaualy identify the requred Sensor and update the variables with your APIs below.
##
##   Reference:
##     - Get Sensor Kit and Configuration Links - https://developer.carbonblack.com/reference/carbon-black-cloud/workload-protection/latest/sensor-lifecycle-management/#get-sensor-kit-and-configuration-links
##     - Check Sensor versions here - https://docs.vmware.com/en/VMware-Carbon-Black-Cloud/index.html
##     - Use the following URL
##       EAP01: https://defense-eap01.conferdeploy.net
##       Prod 01: https://dashboard.confer.net
##       Prod 02: https://defense.conferdeploy.net
##       Prod 05: https://defense-prod05.conferdeploy.net
##       Prod 06: https://defense-eu.conferdeploy.net
##       Prod NRT: https://defense-prodnrt.conferdeploy.net
##       Prod Syd: https://defense-prodsyd.conferdeploy.net
##       Prod UK: https://ew2.carbonblackcloud.vmware.com
##       AWS GovCloud (US): https://gprd1usgw1.carbonblack-us-gov.vmware.com
##    - Postman - https://www.postman.com/vmware-carbon-black/workspace/vmware-carbon-black/request/28313458-9ac920b7-ee83-4125-965d-b45baf6480b5?ctx=documentation
##
##   Improvements;
##
##     - Download the file to a specific location using urllib or wget
##     - Install the sensor within the same script us using OS subprocess
##     - Run the Carbon Black installer
##         https://community.carbonblack.com/t5/Knowledge-Base/Carbon-Black-Cloud-How-to-Perform-an-Unattended-Installation-of/ta-p/65874
##         Replace 'your_msi_file.msi' with the actual MSI file name
##         msi_file = 'your_msi_file.msi'
##         Replace '/qn' with the actual silent installation switch
##         silent_switch = '/qn'
##         Run the MSI executable with the silent installation switch
##         subprocess.call(['msiexec', '/i', msi_file, silent_switch])
##         msiexec.exe /q /i <Sensor Installer Path> /L*v msi.log COMPANY_CODE="XYZABC" CLI_USERS=<UserGroupSid> POLICY_NAME="<NAME Virtual Policy>"
##     - Automatically detect the Operating System and download the correct sensor using  the platform libary.
##        import platform
##        platform.system(),platform.architecture()
##     - Set the expiry automatically + 30 mins
##
##     Version Control
##
##     28.12.2023 - Basic version 
