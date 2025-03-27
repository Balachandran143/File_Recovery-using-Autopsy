# File_Recovery-using-Autopsy

## Aim
The objective of this guide is to demonstrate how to:  
 - Create a **Virtual Hard Disk (VHD)**.  
 - Add images to the disk, delete them, and recover them using **Autopsy**.  
 - Understand the forensic recovery process for deleted files.  
 - Learn how to remove the virtual disk after completing the experiment.

## Virtual Disk Creation & File Recovery using Autopsy 


## Step 1: 
   Create a Virtual Hard Disk (VHD) 

### **1. Open Disk Management**  
- Press **Windows + X** → Click **Disk Management** 

 ![Screenshot 2025-03-20 140749](https://github.com/user-attachments/assets/9b1b5cfe-c9b0-4e3c-ba4c-c0249e628d56)

### **2. Create a New VHD**  
- Click **Action** (top menu) → **Create VHD**.  

![Screenshot 2025-03-20 140950](https://github.com/user-attachments/assets/422ae541-f595-4a84-9b73-60e5524759f1)


### **3. Choose File Location & Size**  
- Click **Browse** and select where to save the VHD file (e.g, `C:\new VHD.vhd`)
- Set the **size** (e.g: `1GB`) 
- Choose **VHD (Fixed Size)** and Click **OK**

![Screenshot 2025-03-20 141038](https://github.com/user-attachments/assets/3c9b0fbf-0969-4ba6-8263-a0ef832d1cdd)


### **4. Initialize the Disk**  
- In **Disk Management**, find your new disk (marked as "Not Initialized").  
![Screenshot 2025-03-27 135007](https://github.com/user-attachments/assets/549d8952-7640-466e-b3f1-3030554e6de0)

- Right-click the disk → Click **Initialize Disk**.

![Screenshot 2025-03-20 141106](https://github.com/user-attachments/assets/7f7e457e-7fd3-4857-b28f-7500e5922f2b)

- Select **MBR (Master Boot Record)**. 

![Screenshot 2025-03-20 141127](https://github.com/user-attachments/assets/37969803-2fba-47d0-ad93-18dbc5343575)


### **6. Create & Format the Partition**  
- Right-click the **Unallocated Space** → Click **New Simple Volume**.  
![Screenshot 2025-03-27 134031](https://github.com/user-attachments/assets/64414bbf-e1f8-46fd-8a8c-f6b4fe80b448)
![Screenshot 2025-03-20 141152](https://github.com/user-attachments/assets/2a718a5b-6747-44dd-b5fd-e2714f449bb8)
![Screenshot 2025-03-20 141200](https://github.com/user-attachments/assets/1e0872c7-bd66-4ae4-b8a3-81da9e4c21c8)



- Click **Next** → **Click on Mount in the following empty NTFS folder** → **Browse** → **Assign a drive letter (e.g., `C: or D:`)** → **New folder** → **OK**
![Screenshot 2025-03-20 141217](https://github.com/user-attachments/assets/c5526e6d-5a34-454c-a3da-ff3d63cd7bd1)

![Screenshot 2025-03-20 141225](https://github.com/user-attachments/assets/1c313b18-f6db-4f98-974a-e32d6456dfcc)

![Screenshot 2025-03-20 141309](https://github.com/user-attachments/assets/85b2a19c-5f63-49ea-b665-8b8fd4881541)

- Click **next** → **Finish**. 

---

## **Step 2: Add & Delete Files for Recovery** 

### **1. Copy Files to the Virtual Disk**  
- Open **File Explorer** → Go to the new drive (`C: or D:`), where the folder created in the previous step
- Create a new folder (`TestFolder`) and copy **images or files** into it.  

### **2. Delete the Files**  
- Select any one or two images → Press **Delete**.  
- Empty the **Recycle Bin** to permanently delete them.  

---

## **Step 3: Recover Deleted Files Using Autopsy**  
### **1. Open Autopsy & Create a New Case** 

- Launch **Autopsy** and **Run as a administrator**  
- Click **Create New Case**.  

![Screenshot 2025-03-20 142228](https://github.com/user-attachments/assets/71f5ce8d-9798-444d-a071-e1d82a0bdfdb)


- Enter a **Case Name** (e.g., `Autopsy1`).  
- Choose a **Case Folder** location.  
- Click **Next** → Click **Finish**.  

![Screenshot 2025-03-20 142324](https://github.com/user-attachments/assets/b8f6d512-a53e-447b-b74e-5d43abafa6b1)


### **2. Add the Virtual Disk as an Evidence Source**  
- Click **Add Data Source**  → **Select Host**
![Screenshot 2025-03-20 142523](https://github.com/user-attachments/assets/68f9a464-19be-4a04-aac0-0de2cd6bdf4b)


- Select **Local Disk** → **next** 

![Screenshot 2025-03-20 142541](https://github.com/user-attachments/assets/f76ff460-e0cc-4d0c-a3c1-7e691b694d97)

- Select Disk → **Choose the VHD drive (`Drive1`)**
![Screenshot 2025-03-20 142638](https://github.com/user-attachments/assets/8c06d523-a356-485c-97ed-e56ef0925ba7)


- Click **Next** → Keep default settings → Click **Finish**.  
- Wait for Autopsy to process the disk.  

### **3. Recover Deleted Files**  
- Go to **File Views** (left panel).  

![Screenshot 2025-03-20 142746](https://github.com/user-attachments/assets/b4f20e8f-5f93-49c5-ad84-073ab8eb73f7)

- Click **Deleted Files** → Find your deleted images.  
- Right-click an image → Click **Extract File**.  
![Screenshot 2025-03-20 142824](https://github.com/user-attachments/assets/eb910faf-c668-48b0-bddf-47365bfaad5a)


- Select a folder to see the recovered files (e.g., `C:\image_recovery`).  

**Your deleted images are now recovered!**  

---

## **Step 4: Delete the Virtual Disk (Optional Cleanup)** 

### **1. Detach the VHD**  
- Open **Disk Management** (`Win + X` → Disk Management).  
- Find the **virtual disk** (`C: or D:`).  
- Right-click the disk (not the partition) → Click **Detach VHD**.  

### **2. Delete the VHD File**  
- Open **File Explorer**.  
- Go to the location where you saved the `.vhd` file (e.g., `C:\new VHD.vhd`).  
- **Delete** the `.vhd` file.  
- Empty the **Recycle Bin**.  

**Your virtual disk is completely removed!**  
 
---
 

## Result :
 This guide covers creating a Virtual Hard Disk (VHD), adding, deleting, and recovering images using Autopsy, and safely deleting the virtual disk after the experiment.
