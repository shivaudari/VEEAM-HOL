![veeam1](./images/veeam1.jpg)
#  Veeam Hands-on Lab for Microsoft Azure
## Login to Azure portal
1. Once the VM is launched, open the Edge browser shortcut named **Azure Portal**

 ![veeam134](./images/veeam134.jpg)
 
2. Click on the **Environment details** and followed by **Azure Credentials**  login with the **Username** and **Password**

 ![veeam135](./images/veeam135.jpg)
 
3. Login to Azure Portal.

 ![veeam136](./images/veeam136.jpg)

## Deploy Veeam VM

1. After login in to the Azure Portal. Search for **Veeam Backup for Microsoft Azure Free Edition** in search bar and click on **Veeam Backup for Microsoft Azure Free Edition**

![veeam127](./images/veeam127.jpg)

2. Click on **Create**

![veeam128](./images/veeam128.jpg)

3. Enter the below details for virtual machine
   `````
   Resource Group: Veeam
   Virtual machine name: Veeam
   Region: EastUS2
   Size: Standard_DS1_V2
   Username: demouser
   Password: Password.1!!
   
   `````

![veeam104](./images/veeam104.jpg)

4. Click on **Review+Create** and then Click on **Create**

![veeam105](./images/veeam105.jpg)

5. Make sure that deployment status is **Success**

![veeam106](./images/veeam106.jpg)

6. Once the deployment got succeeded, click on **Go to resource** or search for the **Virtual Machines** in search bar.

![veeam107](./images/veeam107.jpg)   

7. Select the Virtual machine with the name **Veeam**

![veeam108](./images/veeam108.jpg)

8. Select the Overview and copy **Public IP Address**

![veeam109](./images/veeam109.jpg)

**Note**: Wait for **3 minutes** before moving to the next step

## Login to Veeam VM
1. Open the new/incognito browser and paste the value copied below and replace the **IPADDRESS** with the Veeam VM Public IP Address
  `````
  https://IPADDRESS
  `````
![veeam2](./images/veeam2.jpg)

2. Click on the **advance**

![veeam3](./images/veeam3.jpg)

3. Click on the **continue to IP** to access the website.

![veeam4](./images/veeam4.jpg)

**Note**: Wait till the initial steup completes and status changes to **Success**

![veeam133](./images/veeam133.jpg)

4. Enter the **demouser** for username and **Password.1!!** for Password and click on **Login**

![veeam5](./images/veeam5.jpg)

5. Check all the **Check Boxes** related to licence agreement and click on **Accept** and login into the VM

![veeam6](./images/veeam6.jpg)

## Add a Microsoft Azure Account

1. Click on **Add a Microsoft Azure account first**

![veeam7](./images/veeam7.jpg)

2. Click on **Add**

![veeam8](./images/Veeam8.jpg)

3. Enter the **Name**: **AzureBackup**, **Description**: **Add a Microsoft Azure Account** and click on **Next**
![veeam9](./images/veeam9.jpg)

4. Under **Service Account Type** choose **Specify exisiting service account** and then click on **Next**

![veeam10](./images/veeam10.jpg)

5. Copy the **TenantID**, **Application ID** and **Secret key** of service principal from environment details Tab

![veeam11](./images/veeam11.jpg)

6. Paste the copied values in the respective fields and click on **Next**

   **Note**: Please igore if you get any warning notification.

![veeam12](./images/veeam12.jpg)

7. Move to the **Summary** and click on **Finish** to setup the Microsoft account.

![veeam13](./images/veeam13.jpg)

## Add the Workers to Workspace

1. Go to **Getting Started page** and click on **Review workers configuration**

![veeam14](./images/veeam14.jpg)

2. Click on **+Add**

![veeam15](./images/veeam15.jpg)

3. Click on **Choose** adjacent to **Region** and select the region of the resource group, click on **Apply** and then click **Next**

![veeam16](./images/veeam16.jpg)

4. Select the **Virtual Network**:**Veeam-vnet**, **Subnet**:**default** and **Network security Group**:**veeam-nsg** and **Next**
![veeam143](./images/veeam143.jpg)

5. Click on **Finish**

![veeam19](./images/veeam19.jpg)

6. Click on **Profile** tab on top and click **+Add**

![veeam20](./images/veeam20.jpg)

7. Select the resource group **Region**, click on **Add** and then click on **Next**

![veeam21](./images/veeam21.jpg)

8. Under **Worker Profiles**, leave everything default and click on **Next**

![veeam22](./images/veeam22.jpg)

9. Under **Summary**, click on **Finish** to complete.

![veeam23](./images/veeam23.jpg)

10. Move to **Instances** tab and verify instance is created if it is still in creating state wait until it is **Created**

![veeam24](./images/veeam24.jpg)

## Add repository
1. Move to **Getting Started** page and click on **Add repository**

![veeam25](./images/veeam25.jpg)

2. Click on **+Add**

![veeam26](./images/veeam26.jpg)

3. Enter the **Name**: **AzureBackup** and **Description**: **Creation of repository** and click on **Next**

![veeam27](./images/veeam27.jpg)

4. Select the **Storage account**: **veeamstrDID**, **Container**: **veeamcontainer** and create the new folder with name **azurebackup** and click on **Next**

![veeam28](./images/veeam28.jpg)

5. Go through the configuration under **Option** section and click on **Next**

![veeam28](./images/veeam29.jpg)

6. Click on **Finish** in Summary page.

![veeam30](./images/veeam30.jpg)

7. Verify that the repository creation is **Succeed**.

![veeam31](./images/veeam31.jpg)

## Create Backup policy for Virtual Machines
1. Click on **Configuration** in the upper left corner of screen, click on **Getting started page** and **Create your first policy**

![veeam32](./images/veeam32.jpg)

2. Click on **+Add**

![veeam33](./images/veeam33.jpg)

3. Under **Policy Info** section enter the **Name**: **Virtual Machine Backup** and **Description**: **Creation of Backup for virtual Machine** and click on **Next**

![veeam34](./images/veeam34.jpg)

4. Click on **Azure Active Directory**, select the directory which is given in the azure and select the **Region** same as resource group then click on **Next**.

![veeam35](./images/veeam35.jpg)

5. Click on **Select resources to protect** under **Resource** section. Choose **All resources** and then **Apply** the changes.

![veeam36](./images/veeam36.jpg)

6. Choose **Protect the following resources** and click on **Browse to select the specific resource from the global list**

![veeam37](./images/veeam37.jpg)

7. Check the boxes for **veeamLinux-DID** and **WinVm-DID** and click on Add

![veeam137](./images/veeam137.jpg)

8. Click **Apply**

![veeam39](./images/veeam39.jpg)

9.Click on **Next**

![veeam40](./images/veeam40.jpg)

10. Under **Guest processing** section enable the feature **Enable application-aware snapshots** and click **Next**

![veeam41](./images/veeam41.jpg)

11. **Enable Backups: On** click **Next** under **Targets** section.

![veeam42](./images/veeam42.jpg)

12. Under **Schedule** section, enable **Daily Retension: On** and click om **Edit Daily Settings**

![veeam43](./images/veeam43.jpg)

13. Select the **Repository** : **Azure Backup**, Click on **Apply** and Click **Next**

![veeam44](./images/veeam44.jpg)

14. Under **Settings** leave defaults and click on **Next**

![veeam45](./images/veeam45.jpg)

15. Select the **Cost Estimation** and review the cost estimation and click **Next**

![veeam46](./images/veeam46.jpg)

16. Review the **Summary** section and click on **Finish**

![veeam47](./images/veeam47.jpg)

17. Select the **Checkbox** priority filter and click on **Start**
    **Note**: Wait and proceed after backup is **Successful**

![veeam48](./images/veeam48.jpg)

18. Verify that the backup and snapshot creation is **success**

![veeam49](./images/veeam49.jpg)

## Delete the Windows Virtual Machines
1. Login to the Azure Portal using the credentials from Environment details.

2. Search for the Virtual Machine in Azure search bar and select **winvm-DID** VM and **Delete**.

![veeam138](./images/veeam138.jpg)

3. Select the **Winvm-DID** and check the checkbox for confirmation and click **delete** wait untill it is deleted

![veeam139](./images/veeam139.jpg)

## Restoring the Windows Virtual Machine
1. Navigate to Veeam web portal. Select **Protected Data** and select the restore point of the **winvm-DID**

![veeam52](./images/veeam52.jpg)

2. Click on **Restore** dropdown and then select **VM Restore**

![veeam54](./images/Veeam54.jpg)

3. Select **Winvm-DID** and click **Next**

![veeam55](./images/veeam55.jpg)

4. Under **Account** section click on **Select Account** and **Select Azure Active Directory** then click **Apply** and then **Next**.

![veeam56](./images/veeam56.jpg)

   **Note**: If the Warning window is popup click on **Continue**

5. Within **Restore Mode** select the **Restore to Original Location** and click **Next**

![veeam57](./images/veeam57.jpg)

6. Go to **Reason** provide the **Restore Reason**: **VM deleted** and click **Next**

![veeam58](./images/Veeam58.jpg) 

7. Go through **Summary** and click on **Restore**

![veeam59](./images/veeam59.jpg)

8. Go to Session Logs and verify that VM restore is in success state and Verify **winVM-DID** is recoverd

![veeam60](./images/veeam60.jpg)

## Azure SQL Backup

1. Navigate to **Policies**, select the **Azure SQL** and **+Add**

![Veeam61](./images/Veeam61.jpg)

2. Under **PolicyInfo** section enter value for **Name**: **Sql backup** and **Description**: **Creating Sql backup** and click **Next**

![veeam62](./images/veeam62.jpg)

3. Within **Sources** section click and select the **Azure Active Directory** and click on **Choose regions** under Region.

![veeam63](./images/veeam63.jpg)

4. Select the Resource Group Region, click on **Add** and click on **Apply**

![veeam64](./images/veeam64.jpg)

5. Click on **Resource to Protect**, choose **Protect the following resources** and click on **Browse to select the specifid source from global list**

![veeam65](./images/veeam65.jpg)
![veeam66](./images/veeam66.jpg)

6.Select the **SamepleDB** and click on **Add**, then click on **Apply** and click on **Next**

![veeam67](./images/veeam67.jpg)

7. Under **Processing Options**, select **Use staging servers (recommended for database consistency)** and Click on **Choose server**

![veeam68](./images/veeam68.jpg)

8. Click on **Browse** option for **Staging server** and click on **+Add** for adding SQL account

![veeam69](./images/veeam69.jpg)

9. Provide the details to create Sql account **Name**: **Sql Account** and **Description**: **Create Sql Account** and click on **Next**

![veeam70](./images/veeam70.jpg)

10. Select the Account Enter the **Username**: **sqladmin** ,**Password**: **Password.1!!** and click **Next**

![veeam71](./images/veeam71.jpg)

11. Verify summary and click on **Finish**

![veeam72](./images/veeam72.jpg)

12. Select **Apply** and click **Next**

![veeam73](./images/veeam73.jpg)

13. Under **Schedule**, Enable radio button for **Daily retention** and **Edit Daily Settings**

![veeam74](./images/veeam74.jpg)

14. Select **Repository** for AzureBackup, Click **Apply**  and click **Next**

![veeam75](./images/veeam75.jpg)

15. Leave defaults under **Settings** and click **Next**

![veeam76](./images/veeam76.jpg)

16. Leave defaults within **Cost Estimation** and click **Next**

![veeam77](./images/veeam77.jpg)

17. Verify the summary and click **Finish**

![veeam78](./images/veeam78.jpg)

18. Navigate to **Policies**, select **Azure SQL** and select the **Priority** checkbox then click on **Start**

![veeam79](./images/veeam79.jpg)

19. Make sure that backup is **Success**

![veeam81](./images/veeam81.jpg)

## Delete the SQL Database

1. Navigate to Azure Portal. Select resource group named **veeam** and open the database **SampleDB**

![veeam83](./images/veeam83.jpg)

2. Select the overview of **SampleDB** and then click on **Delete**

![veeam84](./images/veeam84.jpg)

3. Pop-up will appear, within that type in the database name and click on **Delete**

![veeam85](./images/veeam85.jpg)

**Note**: Please wait untill deletion is success

## Recovery of SQL Database

1. Navigate to **Veeam Backup for Microsoft Azure** page. Select the **Protected Data** then select **Azure SQL** option. Within it check the checkbox for **SamepleDB** and click on **restore database** 

![veeam82](./images/veeam82.jpg)

2. Under **Databases**, Select the **SQLdatabase** and Click on **Next**

![veeam86](./images/veeam86.jpg)

3. Under **Accounts**, click on **select the Account**, within it choose an Azure account and click on **Apply**. Select **Next**

![veeam87](./images/veeam87.jpg)

4. Leave defaults within **Restore Mode** and click **Next**

![veeam88](./images/veeam88.jpg)

**Note**: If warning window comes up then click on **Continue**

5. Under **SQL Account**, click on **SqlAccount**, choose an account and click on **Apply**. Select **Next**

![veeam89](./images/veeam89.jpg)

6. Under **Reason**, enter Restore reason as **SQL deleted** and select **Next**

![veeam90](./images/veeam90.jpg)

7. Leave defaults under **Summary** and click on **Restore**

![veeam91](./images/veeam91.jpg)

8. Select **Session Log**. Within it please verify that the SQL Restore Status is showing as **Success** or not, if not then please wait untill it gets succeded.

![veeam92](./images/veeam92.jpg)

## Recovery of files from Linux Virtual Machine.

1. Select **Protected Data**, within it select **Virtual Machines** and then check the checkbox for virtual machine named as **VeeamLinux-DID**. Click on **Restore** and select an option **file-Level-Recovery**

![veeam140](./images/veeam140.jpg)

2. Click on **Change Restore Point**. Specify the restore point where **Backup Destsination** is mentioned as **AzureBackup**. Click on **Apply** and then **Next**.

![veeam94](./images/veeam94.jpg)

3. Under **Restore** enter Restore reason as **Restore File** and select **Next**

![veeam95](./images/veeam95.jpg)

4. Under **Summary**, click on **Start** to initiate the restore.

![veeam96](./images/veeam96.jpg)

5. Under **Protected Data**, within the **Virtual Machines** click on the **FLR** under **File-level Recovery URL** option for the Virtual Machine **VeeamLinux-DID**.

![veeam97](./images/veeam97.jpg)

**Note**: Please wait till the creation of the link.

6. Click on the **URL**. The link will get open in the **New Browser Tab**.

![veeam98](./images/veeam98.jpg)

**Note**: If warning appears stating that **Your connection isn't private** then click on **Advance** and select a link starting with **continue to** as shown in below mentioned screenshot. 

 ![veeam99](./images/veeam99.jpg)

7. Under folder named **disk_0_0**, select the folders **var/lib/waagent/custom-script/download/0**. Check the checkbox for file **text1.txt** and click on **Add to Restore List**

![veeam142](./images/veeam142.jpg)
 
8. Go to **Restore List(1)**, check the checkbox for the file **text1.txt** and click on **Download**
 
 ![veeam101](./images/veeam101.jpg)

## Backup of Azure Files

1. Navigate to **Veeam Backup for Microsoft Azure** page. Close the pop-up window of **File-level Recovery**. Selct **Policies**. Within it select **Azure Files** and click **Add**.

![veeam110](./images/veeam110.jpg)

2. Provide the Policy Name as **azurebackup** and Discripition as **file backup**. select **Next**. 

![veeam111](./images/veeam111.jpg)

3. Under **Sources**, within **Account** click on **Configure account** to choose an Azure account and select **Apply**. Within **Region** choose a region same as Resource Group region. Click on **Add** and **Apply**. 

![veeam112](./images/veeam112.jpg)

4. Within **Resources**, click on **Select resources to protect** and select the Resource type as **File Share**. Click on **Browse to select the specific resource from global list..**, if file share is not available then click on **Rescan** and if available then check the checkbox for the file share. Click on **Add**. Select **Apply** and then **Next**. 

![veeam141](./images/veeam141.jpg)

5. Under **Schedule**, enable an option **Daily retension** and click on **Next**.

![veeam114](./images/veeam114.jpg)

6. Leave defaults under **Settings** and click on **Next**

![veeam115](./images/veeam115.jpg)

7. Under **cost Estimation**, review the cost estimation and click on **Next**.

![veeam116](./images/veeam116.jpg)

8. Under **Summary**, click on **Finish**

![veeam117](./images/veeam117.jpg)

9. Under **Policies**, within **Azure Files**, check if the **Priority** box is checked or not. If not, then check it and Click on **Start**

![veeam118](./images/veeam118.jpg)

10. Make Sure that Snapshot creation is succeeded as shown in below mentioned screenshot.  

![veeam119](./images/veeam119.jpg)

## Recovey of Azure Files

1. Select **Protected Data**, within it click on **Azure Files**, check the checkbox for **File Share**. Click on **Restore** and then **File-Level Restore**.

![veeam120](./images/veeam120.jpg)

2. Under **Account**, click on **Select account..**, choose an Azure account and click on **Apply**. Select **Next**.

![veeam121](./images/veeam121.jpg)

3. Leave defaults under **Restore Mode** and select **Next**.

![veeam122](./images/veeam122.jpg)

4. Under **Reason**, provide Restore reason as **Reason** and click on **Next**.

![veeam123](./images/veeam123.jpg)

5. Under **Summary**, review the configures setting and then click on **Start**

![veeam124](./images/veeam124.jpg)

6. Under **Protected Data**, within **Azure Files** click on the **FLR** under **File-level Recovery URL** option for the File Share **myshare**.

![veeam129](./images/veeam129.jpg)

7. Click on the **URL**. The link will get open in the **New Browser Tab**

![veeam130](./images/veeam130.jpg)

8. Select the folder named **Veeam**. Check the checkbox for the file **file1** and click on **Add to Restore List**

![veeam131](./images/veeam131.jpg)

9. Select the **Restore list(1)**, check the checkbox for **file1**, click on **Restore** and select an option **Keep**.

![veeam132](./images/veeam132.jpg)
