# How to setup a free forever GCP compute engine VM instance

## Follow are the steps to implement the same: -

### Creating the VM Instance

- You need to have a google account to create a GCP VM.
    - Go to google.com and click on "Sign In" on the top right.
    - Click on "Create account" at the bottom left of the box.
        - Choose "For my personal use"
    - Provide all the required details and proceed to the next step when your account has been created.

- Once you have created the google account, go to [google cloud platform](https://cloud.google.com) and click on "Console" on the top right.

- Once on the google cloud console, click on activate free trial button.
    - This will take you to a form where you need to provide your payment and some other details.

- Once you have provided these details, it will take some time to activate your account while google verifies your payment details.

- After this process is done, create a new project by the name of "my-development-sandbox".

- Then delete the "my-project" which is created by default by selecting that project and going to the project settings and shutting down the project from the project settings page.

- The project will be removed after a month automatically.

- After this select your newly created project.

- Select Compute Engine from the left side menu, go to VM instances and enable the compute engine API.

- Go to the compute engine API and click on create VM.

- Name your instance "my-development-sandbox".

- Select one of the regions which are available in GCP free tier. You can separately google for what are the free tier regions at the time of your setting up this whole thing.

- Select machine family as "General Purpose"

- Select series as "N1" and then select Machine Type as "f1-micro"

- Change the boot disk size to 30 GB as that is what you are allowed in free tier at the time of documenting this.

- Click on allow HTTP and HTTPs traffic checkboxes.

- Click on create.

### Creating a billing alert

- Although the VM that you have created is not going to cost you anything as its total cost will remain under the free tier, you shold setup a billing alert.

- Select Billing from the left side menu.

- Then go to Budgets & alerts.

- Create a new budget by the name of "free-tier-budget".

- Keep the time range as "Monthly", select it for all projects, Set the about as 100 Rupees.

- Setup alert triggers for 50%, 90% and 100% budget consumption.

### Setting up a static external IP address so that your VM has a static IP address to connect the domain to

- While your VM is on, go to "VPC Network" on the left menu and select "IP Addresses".

- Go to the "External" IP address associated with your VM and click on the RESERVE button on the right most column of the table.

### Setting up firewall rules for your VM so that it can communicate with the outside world

- Go to the "VPC Network" on the left menu and select "Firewall".

- Click on "Create Firewall Rule" on the top to create a new firewall rule for your needs.

- Ingress are incoming rules to set what to allow for incoming traffic. This will mostly have the https enables for port 443.

- Egress are outgoing rules to set what all data can be allowed to be sent from the VM to the outside world.
