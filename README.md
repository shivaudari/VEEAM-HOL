![veeam1](./images/veeam1.jpg)
#  Veeam Hands-on Lab for Microsoft Azure
## Login to Veeam VM
1. Copy the Public IP address from the VM and Note the **Username** and **Password** from the azure portal
2. Open the new browser and paste the value copied below and replace the **IPADDRESS** with the Veeam VM IP address
  `````
  https://IPADDRESS
  `````
![veeam2](./images/veeam2.jpg)
3. Click on the **advance**
![veeam3](./images/veeam3.jpg)
4. Click on the **click on processed to IP**
![veeam4](./images/veeam4.jpg)
5. Enter the **Username** and **Password** and click on Login
![veeam5](./images/veeam5.jpg)
6. Check all the check boxes in the licence agreement and click on **Accept** and login into the VM
![veeam6](./images/veeam6.jpg)

## Add a Microsoft azure account
1. Click on add a microsoft azure account first
![veeam7](./images/veeam7.jpg)
2. Click on **Add**
![veeam8](./images/Veeam8.jpg)
3. Enter the **Name**, **Description** and click on the **Next**
![veeam9](./images/veeam9.jpg)
4. In the **Service Account Type** click on **Specify the exisiting service account**
![veeam10](./images/veeam10.jpg)
5. Copy the **TenantID**, **Application ID** and **Secret** of service principal from environment details Tab
![veeam11](./images/veeam11.jpg)
6. Paste the Copied values in the respective fields and click **Next**
![veeam12](./images/veeam12.jpg)
7. Move to the **Summary** and click **Finish** to setup the microsoft account
![veeam13](./images/veeam13.jpg)

## Add the Workers to Workspace
1. Go to **Getting Started page** and **click on Review workers configuration**
![veeam14](./images/veeam14.jpg)
2. Click on **+Add**
![veeam15](./images/veeam15.jpg)
3. Click on **region** and select the region of the resource group and **Apply** and Click **Next**
![veeam16](./images/veeam16.jpg)
4. Select the **Virtual Network**, **Subnet** and **Network security Group** and **Next**
![veeam18](./images/veeam18.jpg)
5. Click on **Finish**
![veeam19](./images/veeam19.jpg)
6. Click on **profile** and **+Add**
![veeam20](./images/veeam20.jpg)
7. Select the **Region**, select the proper region and click on **add** and click on **Next**
![veeam21](./images/veeam21.jpg)
8. Move to the **worker profile** and click **Next**
![veeam22](./images/veeam22.jpg)
9. Go to **summary** and click **Finish**
![veeam23](./images/veeam23.jpg)
10. Move to **instance** tab and verify instance is created if it is still in creating state wait till it move to created state
![veeam24](./images/veeam24.jpg)

## Add the repository
1. Move to **Getting Started** page and click on **Add repository**
![veeam25](./images/veeam25.jpg)
2. Click on **+Add**
![veeam26](./images/veeam26.jpg)
3. Enter the **Name** and **Discription** and Click **Next**
![veeam27](./images/veeam27.jpg)
4. Select the **storage account**, **Conatiner** and create the **NewFolder** and **Next**
![veeam28](./images/veeam28.jpg)
5. Select the **Option** and click **Next**
![veeam28](./images/veeam29.jpg)
6. Click on **Summary** and **Finish**
![veeam30](./images/veeam30.jpg)
7. Verify that the repository is creation in success state.
![veeam31](./images/veeam31.jpg)

## Create Backup policy for Virtual Machines
1. Move to **Getting started page** and **Create your first policy**
![veeam32](./images/veeam32.jpg)
2. Click on **+Add**
![veeam33](./images/veeam33.jpg)
3. Click on **PolicyInfo** enter the **Name** and **Description** and click **Next**
![veeam34](./images/veeam34.jpg)
4. Select the **Azure Active Directory**, select the directory which is given in the azure and select the **Region**
![veeam35](./images/veeam35.jpg)
5. Select the  **All resource**
![veeam36](./images/veeam36.jpg)
6. Select the **protect the following resources** and **Browse to select the specific resource from the global list**
![veeam37](./images/veeam37.jpg)
7. Select the checkbox for virtual machine and click on **ADD**
![veeam38](./images/veeam38.jpg)
8. Click on **APPLY**
![veeam39](./images/veeam39.jpg)
9.Click on **Next**
![veeam40](./images/veeam40.jpg)
10. Move to **Guest processing** and **Enable application aware snapshots** and click **Next**
![veeam41](./images/veeam41.jpg)
11. Select the **Targets** and **Enable Backup:on** click **Next**
![veeam42](./images/veeam42.jpg)
12. Select the **Schedule**, **Daily Retension:On** and **Edit Daily Settings**
![veeam43](./images/veeam43.jpg)
13. Select the **Repository** : **Azure Backup**, Click on **Apply** and Click **Next**
![veeam44](./images/veeam44.jpg)
14. Select the **Settings** click **Next**
![veeam45](./images/veeam45.jpg)
15. Select the **Cost Estimation** and review the cost estimation and click **Next**
![veeam46](./images/veeam46.jpg)
16. Select the **Summary** and review the summary and click on **Finish**
![veeam47](./images/veeam47.jpg)
17. Select the **checkbox** for the priority and click on **Start**
![veeam48](./images/veeam48.jpg)
18. Verify that the backup and snapshot creation **success**
![veeam49](./images/veeam49.jpg)

## Delete the Windows Virtual Machines
1. Login to the Azure Portal Using the credentials given in the Environment details.
2. Search for the Virtual Machine in search tab select the  **Veeamwindows** VM and **Delete**.
![veeam50](./images/veeam50.jpg)
3. Select the **Veeamwindows** and check the checkbox for Confirmation and click **delete**
![veeam51](./images/veeam51.jpg)

## Restoring the Windows Virtual Machine
1. Select **Protected data** and select the restore point of the Windows VM
![veeam52](./images/veeam52.jpg)
2. Select **Restore** and then **Restore VM**
![veeam54](./images/Veeam54.jpg)
3. Select **VeeamWindows** and Click **Next**
![veeam55](./images/veeam55.jpg)
4. Goto **Account**, **Select Account**, and **Select Azure Active Directory**, Click **Apply** and Click **Next**.
![veeam56](./images/veeam56.jpg)
5. Go to **Restore Mode** and select the **Restore to Original Location** and click **Next**
![veeam57](./images/veeam57.jpg)
6. Go to **Reason** provide the **Restore Reason** and click **Next**
![veeam58](./images/Veeam58.jpg) 
7. Go to **Summary** and read through the Description and Click on **Restore**
![veeam59](./images/veeam59.jpg)
8. Go to Session Logs and verify that restore is in success state and Verify In the Azure Portal
![veeam60](./images/veeam60.jpg)

## Azure SQL Backup
1. Move to **Policies**, select the **Azure SQL** and **ADD+**
![Veeam61](./images/Veeam61.jpg)
2. Go to **PolicyInfo** Enter Value For **Name** and **Description** and Click **Next**
![veeam62](./images/veeam62.jpg)
3. Select the **Sources** Select the **Azure Active Directory** for Source in the Region select **select region**
![veeam63](./images/veeam63.jpg)
4. Select the **Region** and click on **ADD** and click on **Apply**
![veeam64](./images/veeam64.jpg)
5. Select the **Resource to Protect**, Clink on **protect the following resources** and **Select Browse to select the specifid resource from global list**
![veeam65](./images/veeam65.jpg)
![veeam66](./images/veeam66.jpg)
6.Select the checkbox for the **VeeamSQL** and click on **ADD**, Click on **Apply** and click on **Next**
![veeam67](./images/veeam67.jpg)
7.Select the **Processing Options**, move to **Use staging servers (recommended for database consistency)** and Click on **select server**
![veeam68](./images/veeam68.jpg)
8. Select the **Browse** option for **Staging server** and click on **+ADD** for adding SQL account
![veeam69](./images/veeam69.jpg)
9. Select the **AccountInfo** enter the **Name** and **Description** and click on **Next**
![veeam70](./images/veeam70.jpg)
10. Select the Account Enter the **Username** ,**Password** and click **Next**
![veeam71](./images/veeam71.jpg)
11. Move to **Summary** and click **Next**
![veeam72](./images/veeam72.jpg)
12. Select **Apply** and click **Next**
![veeam73](./images/veeam73.jpg)
13. Select **Schedule**, Enable radio button for **Daily retention** and **Edit Daily Settings**
![veeam74](./images/veeam74.jpg)
14. Select **Repository** for AzureBackup, Click **Apply**  and click **Next**
![veeam75](./images/veeam75.jpg)
15. Goto **Settings** and click **Next**
![veeam76](./images/veeam76.jpg)
16. Move **Cost Estimation** and click **Next**
![veeam77](./images/veeam77.jpg)
17. Move **Summary** and click **Finish**
![veeam78](./images/veeam78.jpg)
18. In the **policies**, click on **Azure SQl** and check the **priority**, Click on **Start**
![veeam79](./images/veeam79.jpg)
19. Make sure that backup is **Success**
![veeam81](./images/veeam81.jpg)

## Delete the SQL Database
1. Move to Azure Portal Search for the **SQL database** and open the database which had **backup**.
![veeam83](./images/veeam83.jpg)
2. Select the overview of **SQL Database** and click on **Delete**
![veeam84](./images/veeam84.jpg)
3. **TYPE THE DATABASE NAME** and click on **Delete**
![veeam85](./images/veeam85.jpg)
**Note**:Wait untill deletion is success

## Recovery of SQL Database
1. Move to **protect data** ,select **Azure SQL**,Select the **checkbox for the Azure SQL** and Click on **restore** 
![veeam82](./images/veeam82.jpg)
2. Goto **Databases**, Select the **SQLdatabase** and Click on **Next**
![veeam86](./images/veeam86.jpg)
3. Goto **Accounts**, **select the Account**, Select the Account given, click **Apply** and **Next**
![veeam87](./images/veeam87.jpg)
4. Goto **Restore Mode**, select the checkbox for **Restore to the original location** and click **Next**
![veeam88](./images/veeam88.jpg)
5. Goto **SQL Account**,select **Account**, click **Apply** and **Next**
![veeam89](./images/veeam89.jpg)
6. Goto **Reason**,**enter Reason** click **Next**
![veeam90](./images/veeam90.jpg)
7. Select **Summary** click on **Restore**
![veeam91](./images/veeam91.jpg)
8. Move to **session log** please verif that Restore is **Success**
![veeam92](./images/veeam92.jpg)
