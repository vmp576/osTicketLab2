<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

# osTicket - Post Installation (Lab 2)

This project concerns the post-installation steps for osTicket after Lab 1 so it can be used properly. Agents, Roles, and Permissions will be configured, as well as various SLA (Service Level Agreement) levels and more.

## Environments and Technologies Used

- Completed osTicket Lab 1 Virtual Machine in VMware

## Operating Systems Used
 - Windows 10 (22H2)

## Project Walk-Through
From Microsoft Edge, enter this link: http://localhost/osTicket/scp/login.php to go into the osTicket Login Page. Log in with the previously configured credentials from the osTicket Lab 1.

<img src="https://i.imgur.com/FpTnwGt.png" height="70%" width="70%"/>

Click on the Admin Panel > Agents > Roles. Create a new role called the Super Admin and assign it every permission from Tickets, Tasks, and Knowledgebase tabs. Then, click Add Role

<img src="https://i.imgur.com/93ROEuC.png" height="70%" width="70%"/>

Select the Departments tab > Add New Department > Name: SysAdmins > Create Dept. After creating the SysAdmins department, delete the Maintenance Department.

<img src="https://i.imgur.com/wahamfM.png" height="70%" width="70%"/>

Now, we will allow anyone to create tickets. Settings > Users > **ENSURE REGISTRATION REQUIRED IN UNCHECKED**

<img src="https://i.imgur.com/JV8SDX8.png" height="70%" width="70%"/>

Now, we will create 2 users. Go to Agents > Add New Agent > Add With Following Parameters:

- Name: Jane Doe
    - Email: janedoe@helper.com
    - Username: janedoe
    - Set Agent Password: **Uncheck** “Send the agent a password”
    - Password: Password123!
    - Require Password Change: **Uncheck**
    - Access > Primary Department: SysAdmins
        - Role: Super Admin
    - Access > Extended Access: Support
        - Role: Super Admin
    - Teams > Assigned Teams > Add New: Online Banking > Add (Ensure Alerts to Online Banking are Enabled)
- Name: John Doe
    - Email: johndoe@helper.com
    - Username: johndoe
    - Set Agent Password: **Uncheck** “Send the agent a password”
    - Password: Password123!
    - Require Password Change: **Uncheck**
    - Access > Primary Department: Support
    - Access > Role: View Only
    - Teams > Assigned Teams: Level I Support

<img src="https://i.imgur.com/IogaDmG.png" height="70%" width="70%"/>

Select Teams. Make sure that both Level I Support and Online Banking each have 1 member. John Doe for Support and Jane Doe for Online Banking. If they do not have any members or if there are any discrepancies, fix them now.

<img src="https://i.imgur.com/vT0L6yk.png" height="70%" width="70%"/>

After creating the agents and verifying the team members, we will now be creating the various SLA levels. From Manage > SLA Add New SLA Plan, create the following SLA severity levels:

- Sev-A (Grace Period: 1 hour, Schedule: 24/7)
- Sev-B (Grace Period: 4 hours, Schedule: 24/7)
- Sev-C (Grace Period: 8 hours, Business Hours)

<img src="https://i.imgur.com/2f0EwKc.png" height="70%" width="70%"/>

Now, we will be creating Help Topics. Go to Manage > Help Topics > Add New Help Topic. Create the following help topics:

- Business Critical Outage
    - Parent Topic: Report a Problem / Access Issue
- Personal Computer Issues
    - Parent Topic: Report a Problem
- Equipment Request
    - Parent Topic: General Inquiry
- Password Reset
    - Parent Topic: Report a Problem
- Other
    - Parent Topic: General Inquiry

<img src="https://i.imgur.com/89W3UK8.png" height="70%" width="70%"/>

Finally, we will work on the Agents Panel to create new users. Select Agents Panel > Users > Add User. Create the following users with these parameters:

- karen@user.com
    - Karen
- ken@user.com
    - Ken

<img src="https://i.imgur.com/AZlx6m8.png" height="70%" width="70%"/>

After completing everything, you can take a snapshot after completing osTicket (Lab 2). This is useful if you want to practice the 3rd osTicket lab consistently without the previous configuration efforts.
