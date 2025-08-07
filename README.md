# Windows-Sever-Backup-Restore

🖥️ Windows Server System Backup and Restore – Practical Summary
This project shows how to create a system backup of a Windows Server and how to restore it later when needed.

✅ What I did:
Took a System Backup (includes system state and essential system files).

Used the Windows Server Backup tool to create the backup.

Saved the backup to a different drive or location.

Planned to restore the server's system using this backup (for recovery purposes).

🎯 Purpose:
To show how to protect the Windows Server system using backup and restore in case of failures or system issues.

## Steps 

1. In this screenshot, I created some users. Later, I will delete them and then restore the system to bring them back.
   
  ![image alt](Images/1.PNG)

2. Click on "Add Roles and Features" to install the Windows Server Backup feature.

  ![image alt](Images/2.PNG)

3. In the Features section, check the Windows Server Backup option, then click Next and proceed with the installation. Once the installation is complete, go to the Tools menu. At the bottom, you will find Windows Server Backup click on it to open.

   ![image alt](Images/3.PNG)

4.Now, click on Local Backup. You will see two options: Backup Schedule (used to configure daily backups) and Backup Once (used for a one-time manual backup). In this practical, I will perform a Backup Once operation.

   ![image alt](Images/4.PNG)

5. Click on Backup Once, then select the Custom option and click Next to proceed.

   ![image alt](Images/5.PNG)

6. Click on Add Items to select the components you want to include in the backup

   ![image alt](Images/6.PNG)

7. Select System State, as this backup will include Active Directory and other essential system services.
   ![image alt](Images/7.PNG)

8. I am going to store the backup on the E: drive, but you can choose any location based on your requirements.

   ![image alt](Images/8.PNG)

9. Now, select your destination drive and click Next to continue.

    ![image alt](Images/9.PNG)

10. On the Confirmation page, click Backup to start the process.

    ![image alt](Images/10.PNG)

11. You can now see that the system backup process has started.

    ![image alt](Images/11.PNG)

12. The system backup has been completed successfully.

    ![image alt](Images/12.PNG)

13. You can see that the backup has been successfully saved to the E: drive.

    ![image alt](Images/13.PNG)

14. Now that the backup is complete, we will delete the users we created earlier. After that, we will proceed with the restoration to recover them.

    ![image alt](Images/14.PNG)

15. Now, open Windows Server Backup and click on Recover to begin the restoration process. 

  ![image alt](Images/15.PNG)

16. To recover the system backup, we must boot into Directory Services Restore Mode (DSRM); otherwise, an error will occur during the restoration process.

🛠️ What is DSRM (Directory Services Restore Mode)?
DSRM (Directory Services Restore Mode) is a special boot mode in Windows Server used for performing maintenance or recovery tasks related to Active Directory.

🔍 Why is DSRM used?
It temporarily disables Active Directory so you can safely perform tasks like:

Restoring system state (e.g., from a backup)

Repairing or recovering Active Directory

Troubleshooting domain controller issues
    ![image alt](Images/16.PNG)

17. To enter DSRM mode, press Windows + R, type msconfig, and press Enter.

    ![image alt](Images/17.PNG)

18. Then, go to the Boot tab, check the Safe boot option, and select Active Directory repair. After that, click Apply, then OK.

    ![image alt](Images/18.PNG)

19. Your system will now restart and boot into Directory Services Restore Mode (DSRM).

    ![image alt](Images/19.PNG)

20. While in DSRM mode, open Windows Server Backup, and click on Recover to begin the restoration process.

    ![image alt](Images/20.PNG)

21. Click Next

    ![image alt](Images/21.PNG)

22. Select the date and time when the backup was created.

    ![image alt](Images/22.PNG)

23. Now, select the type of backup you want to restore. In this case, I am restoring the System State backup.

    ![image alt](Images/23.PNG)

24. Click Next then OK

    ![image alt](Images/24.PNG)

    ![image alt](Images/25.PNG)

25. Now, click on Recover to start the restoration process.

    ![image alt](Images/26.PNG)

26. You can now see that the data recovery process has started.

    ![image alt](Images/27.PNG)

27. Once the recovery is complete, restart your system and exit DSRM mode by following the same steps in msconfig, but this time uncheck Safe boot, then click Apply and OK.

    ![image alt](Images/28.PNG)

28. You can now see that the users we previously deleted have been successfully restored.

    ![image alt](Images/29.PNG)

29. All data has been successfully restored.

    ![image alt](Images/30.PNG)
