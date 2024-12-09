**Here are the steps to modify the AWS instance volume and resize the file system:**

**Step 1: Modify the Volume in the AWS Account**

> Go to EC2 Instance
Log in to your AWS account and navigate to the EC2 dashboard.
Select 'Volumes' under 'Elastic Block Store'
In the left-hand menu, click on "Volumes" under the "Elastic Block Store" section.
Select the desired Volume
Choose the volume you want to modify.
Click on 'Actions' – Click on 'Modify Volume'
Click on the "Actions" dropdown menu and select "Modify Volume".
Enter the total GB you want
Enter the new size for the volume in GB.
Click on Modify
Click the "Modify" button to apply the changes.


**Step 2: Resize the File System on the Server**

**For Ubuntu-based systems using /dev/xvda**
Check the current disk layout.
```javascript
lsblk
```
Grow the partition to fill the available space.
```javascript
sudo growpart /dev/xvda 1
```
Verify the updated disk layout.
```javascript
lsblk
```
Resize the file system to match the new partition size.
```javascript
sudo resize2fs /dev/xvda1
```


**For Ubuntu-based systems using /dev/nvme0n1**
Check the current disk layout.
```javascript
lsblk
```
Grow the partition to fill the available space.
```javascript
sudo growpart /dev/nvme0n1 1
```
Verify the updated disk layout.
```javascript
lsblk
```
Resize the file system to match the new partition size.
```javascript
sudo resize2fs /dev/nvme0n1p1
```
