# 1.  Course: Google Cloud Platform Fundamentals - Core Infrastructure

## Module: Applications in the Cloud (getting started with App engine)

### Objectives (using the cloudshell)
1. Initialize App Engine.

1. Preview an App Engine application running locally in Cloud Shell.

1. Deploy an App Engine application, so that others can reach it.
 


`<gcloud auth list>` - This command will list the active account name. 

`<gcloud config list project>` - This will list available projects associated with the selected account. 

`<gcloud config set project PROJECT_ID>` - This command will set the project with the selected project ID. 


### Initializing App Engine

`<gcloud app create --project=$DEVSHELL_PROJECT_ID>`
a prompt will be displayed to choose the region where the app engine should be created (select your preferred region). 

`<git clone https://github.com/GoogleCloudPlatform/python-docs-samples>` - This will Clone the source code repository for a sample application in the hello_world directory. 

`<cd python-docs-samples/appengine/standard_python3/hello_world>` - Navigating to the source directory. 


### Run the Hello World application locally. 
`<sudo apt-get update>` - This command will download and update the packages list.

`<sudo apt-get install virtualenv>` (If prompted [Y/n], press Y and then Enter.)

`<virtualenv -p python3 venv>`

`<source venv/bin/activate>` - (source venv/bin/activate). 

`<pip install  -r requirements.txt>`- (Navigate to your project directory and install dependencies). 

`<python main.py>` - (Run the application). 

in the Cloud Shell, click Web preview (Web Preview) > Preview on port 8080 to preview the application. This is to verify that the app is running. 

To end the test, return to Cloud Shell and press Ctrl+C to abort the deployed service. 

Using the Cloud Console, verify that the app is not deployed. In the Cloud Console, on the Navigation menu (Navigation menu), click App Engine > Dashboard.

### Deploy and run Hello World on App Engine. 

To deploy the application to the App Engine Standard environment:


`<cd ~/python-docs-samples/appengine/standard_python3/hello_world>` - (Navigate to the source directory)

`<gcloud app deploy>` - (this command Deploys your Hello World application). 

If prompted "Do you want to continue (Y/n)?", press Y and then Enter.

This app deploy command uses the app.yaml file to identify project configuration.


`<gcloud app browse>` 

Launch your browser to view the app at http://YOUR_PROJECT_ID.appspot.com

Copy and paste the URL into a new browser window. The app is now deploy an will be viewable/accessible through the url. 



# 2.  Course: Google Cloud Platform Fundamentals - Core Infrastructure


## Module: GCP Fundamentals: Getting Started with Compute Engine -


### Objective
Create a Virtual Machine using the Gcloud command line.

Start by setting and selecting the account & project ID in the the VM will run on. 

`<gcloud auth list>` - This command will list the active account name. 

`<gcloud config list project>` - This will list available projects associated with the selected account. 

`<gcloud config set project PROJECT_ID>` - This command will set the project with the selected project ID. 



### create the VM With the following command

step 1:
Display a list of all the zones in the region to which the project is associated with the command `gcloud compute zones list`

step 2:
Set your default zone to the preferred one from the previous list with the command gcloud config set compute/zone followed by the zone you chose. 
eg. gcloud config set compute/zone us-central1-b

step 3:
To create a VM instance called my-first-vm in that zone, execute this command

gcloud compute instances create "my-first-vm" \
--machine-type "n1-standard-1" \
--image-project "debian-cloud" \
--image "debian-9-stretch-v20190213" \
--subnet "default"

This will create a Virtual Machine with the name 'my-first-vm" in using the default VPN network and the default firewall rules set under the VPC network. 




