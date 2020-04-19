---
topic: "MongoDB: Cloud Atlas Setup"
desc: "Setting up MongoDB Cloud Atlas (for new users)"
category_prefix	: "MongoDB: "
indent: true
---

The current recommended MongoDB installation for CS48 is MongoDB Cloud Atlas.

The instructions in this article cover how to set up a new free account, up to the step where you get a MongoDB URI connection string.

# Step 1: Create free account

  Navigate to <https://mongodb.com/cloud/atlas> and click the "Start&nbsp;Free" button.

  ![00-mongo-db-atlas-start-free.png](00-mongo-db-atlas-start-free-30.png)

# Step 2: Fill out the form

  Fill in the form. We encourage you to use your `@ucsb.edu` account.

  ![01-get-started-free-form.png](01-get-started-free-form-30.png)

# Step 3: Choose the Free Plan

  The next page asks you to choose from among various plans.  Naturally,
  you should choose the free plan, so click the "Create&nbsp;a&nbsp;cluster"
  button in that column.
  
  ![03-choose-account-type.png](03-choose-account-type-30.png)

  ![04-choose-free-plan.png](04-choose-free-plan-30.png)

# Step 4: Choose a cloud provider

  MongoDB Cloud Atlas runs, under the hood, on other cloud providers: Amazon, Google, and Microsoft's platforms.   The default is Amazon, and you need to choose either US East, or US West.

  ![05-choose-cloud-provider.png](05-choose-cloud-provider-30.png)

  If you are located in California, there may be some marginal performance benefit to choosing US West, 

  ![06-select-us-west.png](06-select-us-west-30.png)

  Click the "Create Cluster" button.  This will launch Cluster Creation,
  described in the next step.

# Step 5: Cluster Creation

  At this point, there is about a 3 minute wait while your cluster is being
  created.  The screen will look like this, with a blue progress bar
  at the top, and a note that your cluster is being created in the center
  of the screen.  

  ![07-cluster-creation.png](07-cluster-creation-30.png)

  You can wait, or periodically refresh your page, until it looks like this.
  This is your indication that cluster creation is finished:

  At this point you are ready to click the "Connect" button
  as shown below.

  ![08-cluster-creation-done.png](08-cluster-creation-done-30.png)

  That should take you to this screen, which will be described in the next
  step.

  ![09-connect-to-cluster.png](09-connect-to-cluster-50.png)

# Step 6: Whitelist Current IP Address

  ![09a-connect-to-cluster.png](09a-connect-to-cluster-50.png)

  When you click on the "Add Your Current IP Address" button, you'll
  be deposited at this screen.   Add a description of the machine
  and internet connection you are currently using, and click "Add IP Address".

  ![10-whitelist-current-ip-address.png](10-whitelist-current-ip-address-50.png)

  Note that this will *only* whitelist
  the IP address of the computer on which you are running the web browser.

  This should allow you to connect to the MongoDB database from your
  application when running on `localhost` on that same computer.
  
  It will *not* however, allow access from:
  * cloud platforms such as now.sh
  * your same laptop, if it changes IP address (e.g. if you move from one
    network to another, or if your ISP changes your apparent public IP address
    from time-to-time).

  Therefore, you may need to return to this screen later to whitelist
  additional IP addresses.

# Step 8: Whitelist the Entire Internet (not a "best practice")

  Although it is not the "best practice" in terms of security,
  the easiest way to proceed is to whitelist the "entire internet".

  The more secure alternative is to whitelist:
  * Specfic addresses for the IP addresses you may have when you are
    doing development.
  * Specific address ranges for cloud providers such as `now.sh` and/or Heroku

  That is more secure, but it can be tedious and error prone.

  So, to whitelist the entire internet, proceed as follows:
  
  Access the menu item on the left for "Network Access",
  and then click the button to "ADD IP ADDRESS".

  ![Select Add IP Address](10b-allow-access-from-anywhere-50.png)


  In the screen that comes up, there is a button for
  "Allow Access from Anywhere". This automatically enters the
  address block `0.0.0.0/0`, which is the standard notation for
  "All IPv4 addresses", i.e. the entire Internet.

  Click "Confirm" and then your MongoDB database will be accessible
  from anywhere.

  ![Allow Access from Anywhere](10b-allow-access-from-anywhere.png)

# Step 8: Create a MongoDB User

  ![11-create-a-mongodb-user.png](11-create-a-mongodb-user-50.png)

  ![12-ready-to-connect.png](12-ready-to-connect-50.png)

# Step 9: Obtain the URI string for connection 

  ![13-connect-your-application.png](13-connect-your-application-50.png)

  ![14-connection-string-node-3.0.png](14-connection-string-node-3.0-50.png)

  ![15-database-access-menu-item.png](15-database-access-menu-item-50.png)

  ![16-database-access-screen.png](16-database-access-screen-50.png)

# Step 10: Obtaining (changing) the DB User Password

  ![17-edit-user.png](17-edit-user-50.png)

  ![18-change-db-user-password.png](18-change-db-user-password-50.png)

  ![19-edit-mongodb-uri-with-password-holder.png](19-edit-mongodb-uri-with-password-holder-50.png)

  ![20-copy-password.png](20-copy-password-50.png)

  ![21-paste-in-password.png](21-paste-in-password-50.png)