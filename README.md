<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<p>
  
<h1 align="center">osTicket - Post-Install Configuration</h1>
This tutorial guides you through the process of configuring osTicket, an open-source help desk ticketing system, after it's been installed. It's important to note that this tutorial assumes you've already completed the installation, set up your login credentials, and performed necessary cleanup steps within your Virtual Machine environment. These prerequisites were covered in a previous tutorial titled <a href ="https://github.com/cyber-singh/osticket-prereqs">"osTicket - Prerequisites and Installation"</a><br />
</p>

****
<p>
<h2>Environments and Technologies Used</h2>
  
  Before we dive into the configuration process, let's take a look at the environments and technologies involved:

 - **Virtual Machine Platform:** Microsoft Azure (Virtual Machines/Compute)
 - **Access Method:** Remote Desktop
 - **Web Server:** Internet Information Services (IIS)
 - **Ticketing System:** osTicket
 - **Operating System:** Windows 10

</p>

</br>

<p>
  <h2>Post-Install Configuration Objectives</h2>
  
  **1. Familiarize with osTicket's User Interface:** Get to know the layout and features of osTicket's user interface.

  **2. Create and Configure Roles:** Assign specific permissions to agents within their respective departments.

  **3. Ticket Creation:** Understand how to create tickets effectively.

  **4. Agent and User Management:** Learn how to set up agents and users for efficient ticket handling.

  **5. Service Level Agreements (SLA Plans):** Configure SLA plans to manage ticket response times.

  **6. Help Topic Configuration:** Set up help topics to streamline the ticket submission process.
  
  Now, let's proceed to the actual configuration steps:
</p>

</br>

<p>
  <h2>Configuration Setups</h2>
  
  To get started, open your web browser and access osTicket. Log in using the credentials you created in the previous tutorial.

  **Note:** When using osTicket, you'll come across two panels. The **Agent Panel** and the **Admin Panel**. You can determine which panel you are currently on by checking the label in the top right corner of the user interface, located next to your user login name. As an example, if you see the label **"Admin Panel"**, you are in the **"Agent Panel"** and Vice Versa.
</p>

<br>

<p>
  
  - In this example, the user **"josh"** is on the Agent Panel
  
    <img src="https://github.com/cyber-singh/post-install-config/assets/149118027/9e560b66-9fd6-49f1-991a-30f6aeacae60"/>

    <img src="https://github.com/cyber-singh/post-install-config/assets/149118027/1f3b7eb2-bfd7-46ad-8118-fae12dc1f926"/>    
</p>

****

<p>
<h2>Configuring Roles, Departments, & Teams</h2>

<h3>Roles:</h3>

 - Roles are crucial for assigning specific permissions to agents within their departments.
 - To create a new role, navigate to the **Admin Panel**, go to **Agents**, and select **Roles**. Click **"Add New Role"**, and specify the role's **Name and Permissions**.
<br>

**Note:** osTickets creates four Roles (All Access, Expanded Access, Limited Access, and View Only) by default.

<img src="https://github.com/cyber-singh/post-install-config/assets/149118027/68a1f67a-86a9-4a21-956a-0afc55c7af14"/>
</p>
<br>

<p>
  
 - Name the new Role **Supreme Admin**.

   <img src="https://github.com/cyber-singh/post-install-config/assets/149118027/53fb7cae-3e77-489e-93b6-cda2573662d7"/>
</p>

<p>
  <br>
  
 - Navigate to the **"Permissions"** tab, where you can assign precise permissions to this role. For the **"Supreme Admin"** role, we will check all the checkboxes under the **"Tickets"**, **"Tasks"**, and **"Knowledgebase"** sections. Finally, click on **"Add Role"** to complete and create the role.

   <img src="https://github.com/cyber-singh/post-install-config/assets/149118027/7dce691b-7bc3-4e9b-8e24-c84f84e2de62"/>
  
</p>

****

<p>

  <h2>Departments</h2>

 - Departments play a vital role in routing and resolving tickets based on their importance and specific instructions.
 - Create a new department through the same Agents tab. Navigate to the **"Departments"** tab and click on **"Add New Department"**.
<br>

</p>

<p>
  
**Note:** Much like Roles, osTicket also creates two Departments **Maintenance** and **Support** by default.

 <img src="https://github.com/cyber-singh/post-install-config/assets/149118027/06727f1a-b130-4a02-bffe-9da229658e29"/>
</p>

<p>
  
<br>

 - Name the Department **System Administrators** (we'll leave everything else by default for now), then click on **Create Dept** to create Department.

    <img src="https://github.com/cyber-singh/post-install-config/assets/149118027/1906c7bf-57cf-4499-a56a-0d5a24f925a3"/>
</p>

****

<p>
<h2>Teams:</h2>

 - Teams provide a way to organize agents from different departments to handle specific issues and override department-specific rules.
 
 - In the **Agents tab**, click on **Teams**, then select **"Add New Team"** to create a new team.

<br>

**Note:** Just like previous set ups, osTicket creates a **Team (Level I Support)** by default.
  
<img src="https://github.com/cyber-singh/post-install-config/assets/149118027/f3cfe6ea-03a6-4f38-8bd9-0e7160eaf8ff"/>
 </p>

<br>

<p>
  
 - Name the Team **Level II Support** then click on **Create Team** to create the Team.

    <img src="https://github.com/cyber-singh/post-install-config/assets/149118027/14fcef36-33d0-47a1-8d02-29181c20b4ed"/>
</p>

****

<p>
<h2>Allowing Anyone to Create Tickets</h2>

 - In the **Admin Panel**, under the **Settings** tab, navigate to **Users**. Ensure that the **"Registration Required"** option is unchecked. This allows ticket creation without requiring user registration.

   <img src="https://github.com/cyber-singh/post-install-config/assets/149118027/c9f8a5c5-3b8a-4adc-b43c-e92550e674bb"/>
   
</p>

****

<p>
<h2>Adding Agents and Users</h2>
  
<h3>Adding Agents:</h3>

 - Agents, also known as workers,  are given the access to the help desk in osTicket to respond, resolve, and update the status of tickets.
 - To add new agents, go to the Admin Panel, click on Agents, and select "Add New Agent."

   <img src="https://github.com/cyber-singh/post-install-config/assets/149118027/4706f523-b39a-4c0b-9945-10c5defc4827"/>
<br>

</p>

<p>
  
 - In this tutorial, we'll create two new Agents, **Jane** and **John**. It's a good idea to have a notepad ready to record their login information. We'll use the usernames **[name].doe** and set both of their passwords to **Password1** for convenience (which is the same as our admin password from the installation tutorial).
 
 - **Here are the steps:**

1. Fill in the Agent's basic information, and set the Agent's email address as **[name].doe@osticket.com**. Then, click on **"Set Password"**.

   <img src="https://github.com/cyber-singh/post-install-config/assets/149118027/7ea0f110-93a3-43ef-8d2a-b01fdf6159cd"/>
</p>

<br>

<p>
  
2. Set the Agent's password to **"Password1"** and **Uncheck** the boxes to prevent the Agent from needing to reset the password or change it after login.

   <img src="https://github.com/cyber-singh/post-install-config/assets/149118027/25ad4be8-3197-48c7-99b7-55ac94bc68d5"/>
</p>

</br>

<p>
  
3. Next, go to the **"Access"** tab to set the Agent's **"Primary Department"** (which is mandatory to create the Agent). You can also add **"Extended Access"** to allow the Agent to access additional Departments.

   <img src="https://github.com/cyber-singh/post-install-config/assets/149118027/ce18f736-41b3-4247-aad5-54c615175104"/>
</p>

<br>

<p>
  
**NOTE:** Optionally, you can head to the **"Teams"** tab to assign the Agent to a specific team.
</p>

****

    <ul>
    <li></li>
    </ul>
    <li>OPTIONAL: Head to the <b>Teams</b> tab to assign the Agent to a Team</li>
   </p>
<p>
  
<br>










<h3>Adding Users:</h3>

 - Users, or customers, create and own tickets.  They can also track their ticket status.
 - Access the Users tab in the Agent Panel and click on "Add User" to create new users.
 - Follow these steps to effectively manage both agents and users.

  





</p>


    <li>For this tutorial, we will be creating two new Agents <b>Jane</b> and <b>John</b>, it is advise to have a notepad ready to catalog login information as you enter their credentials, but we will set their user names as <b>[name].doe</b> and both of their passwords as <b>Password1</b> for convenience (which is our admin password from the installation tutorial)</li>
    <ul>
      <li>Fill in the Agent's basic info and set the Agent's email address as <b>[name].doe@osticket.com</b> and click on <b>Set Password</b></li>
      <li><img src="https://github.com/cyber-singh/post-install-config/assets/149118027/7ea0f110-93a3-43ef-8d2a-b01fdf6159cd"/></li>
      <li>Set the Agent's password to <b>Password1</b> and unchecked the boxes to prevent the Agent for our example from needing to reset password or change password after login</li>
      <li><img src="https://github.com/cyber-singh/post-install-config/assets/149118027/1a220861-86c2-4b21-8f9e-067e545dc715"/></li>
    </ul>
    <li>Go the <b>Access</b> tab to set the Agent's <b>Primary Department</b> (Mandatory to create the Agent). <b>Extended Access</b> can also be added to the Agent in order to access additional Departments</li>
    <ul>
    <li><img src="https://github.com/cyber-singh/post-install-config/assets/149118027/ce18f736-41b3-4247-aad5-54c615175104"/></li>
    </ul>
    <li>OPTIONAL: Head to the <b>Teams</b> tab to assign the Agent to a Team</li>
  </ul>
  
  <li><b>Users</b> (or Customers) are creators and owners of tickets and by using osTicket they are able to track the status of their tickets</li>
  
  <ul>
    <li>In the <b>Agent Panel</b>, go to the <b>Users</b> tab and click on <b>Add User</b></li>
    <ul>
      <li><img src="https://github.com/cyber-singh/post-install-config/assets/149118027/14e0ed5a-189a-4e65-b9f1-05d16e816027"/></li>
    </ul>
    <li>For this tutorial, we will be creating two new Users <b>Ken</b> and <b>Karen</b> and setting up usernames, emails, and passwords similar to our Agents.</li>
    <ul>
      <li><img src="https://github.com/cyber-singh/post-install-config/assets/149118027/c3dd9d8c-e64d-4dae-8b16-8deef92bf41c"/></li>
    </ul>
  </ul>
  
</ul>
  
</p>

</br>

<h3>Adding SLA Plans</h3>

<p>
  
<ul>
  <li><b>Service Level Agreements</b> or SLA Plans provide a length of time for the ticket Administrator when the ticket is expected be CLOSED. They can also be designated to specific Departments or Help Topics</li>
  <li>In the <b>Admin Panel</b>, go to the <b>Manage</b> tab and drop down to <b>SLA</b> then click on <b>Add New SLA Plan</b></li>
  <ul>
    <li><img src="https://github.com/cyber-singh/post-install-config/assets/149118027/e76fc18a-6676-4b87-a3de-7b986e2206e2"/></li>
    <li><img src="https://github.com/cyber-singh/post-install-config/assets/149118027/88409634-f17f-4b24-9388-cc791f7a87a2"/></li>
  </ul>
  <li>osTicket by default has the SLA Plan <b>Default SLA</b>. We will be creating three SLA Plans each with their own length of time for different kinds of importance of the ticket, from highest priority to lowest priority:</li>
  <ol>
    <li>SEV-A with <b>1 hour Grace Period, 24/7 Schedule</b>, suitable for tickets that are business critical</li>
    <li>SEV-B with <b>4 hour Grace Period, 24/7 Schedule</b>, suitable for tickets affecting employees such as troubleshooting or PC problems</li>
    <li>SEV-C with <b>8 hour Grace Period, business hours Schedule</b>, suitable for tickets requesting new equipment</li>
  </ol>
  <li>Example of creating SEV-A SLA Plan, click on <b>Add Plan</b> to create the SLA Plan</li>
  <ul>
    <li><img src="https://github.com/cyber-singh/post-install-config/assets/149118027/875afb75-7833-4bef-a940-b7824b74aa1f"/></li>
  </ul>
</ul>
  
</p>

</br>

<h3>Configuring Help Topics</h3>

<p>
  
<ul>
  <li><b>Help Topics</b> are helpful to streamline the ticket entry experience for the user by helping them specify their ticket info and also determine what Department the ticket should go to</li>
  <li>In the <b>Admin Panel</b>, go to the <b>Manage</b> tab and click on <b>Add New Help Topic</b></li>
  <ul>
    <li><b>Note</b>: osTicket creates four Help Topics (Feedback, General Inquiry, Report a Problem, and Report a Problem / Access Issue) by default</li>
    <li><img src="https://github.com/cyber-singh/post-install-config/assets/149118027/2475b22a-27d3-4fdc-9b1f-40d434d8b0af"/></li>
  </ul>
  <li>We will create four different Help Topics based on the potential serverity a ticket could have, from highest to lowest priority:</li>
  <ol>
    <li>Business Critical Outage</li>
    <li>Personal Computer Issues </li>
    <li>Equipment Request</li>
    <li>Password Reset</li>
  </ol>
  <li>Example of entering credentials for the Help Topic "Equipment Request," click on <b>Add Topic</b> to create the Help Topic</li>
  <ul>
    <li><img src="https://github.com/cyber-singh/post-install-config/assets/149118027/b004bb9f-336c-46f8-81e7-d12f1127bd33"/></li>
  </ul>
  
</ul>
  
</p>

</br>

<h3>Further Reading and Manual</h3>
<ul>
  <li>This concludes to basics of osTicket configuration, but further information and research on the features of osTicket can be found in the official online documentation <a href= "https://docs.osticket.com/en/latest/index.html">here</a></li>
</ul>

<br/>

<h3 align = "right">Next Tutorial - <a href = "https://github.com/cyber-singh/ticket-lifecycle">osTicket: Ticket Lifecycle Examples</a></h3>  
