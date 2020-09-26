
# Lebanon Relief Network

![AW-c_logo](logo1.png)
![LRN_logo](LRN_logo.png)

## Contents

1. [Submission](#submission)
1. [Demo video](#demo-video)
1. [The architecture](#the-architecture)
1. [Long description](#long-description)
1. [Project roadmap](#project-roadmap)
1. [Getting started](#getting-started)
1. [Live demo](#live-demo)
1. [Built with](#built-with)
1. [Version](#versioning)
1. [Authors](#authors)
1. [License](#license)

## Submission

### Lebanon Relief Network - An Al-Wasl.connect extension

Short description

### How can Al-Wasl.connect-LRN platform help?

Long Description

### The LRN team

Team

## Solution

- Platform description + scope

### Roadmap
- Design thinking
- development
- User impact
- Donation to NGOs

### Code
- GitHub repo

### Video
[Here](https://ibm.box.com/s/f0c6ho9ca6p5gw3o1k8u3dp1lfkn7o64)

## Solution Architecture

![image](LRN + al.wasl-connect architecture.png.jpeg)

### IBM Cloud Services
- List of Cloud services used

## Db2 service:
All csv are available [here](https://github.com/Call-for-Code/Al-Wasl.Connect/tree/master/data)
1.	Search db2 service(simple), select __lite plan__ and create.
1.  First step is to create __service credentials__
1.	Open db2 service from resource list and from left menu __service credentials__, click __new credentials__ and then add. (We will use these credentials in .env file)  
1.  Now lets open db2 console, click __manage__ from left menu and select __Open Console__
1.	Select three dots on top left, then click __Load Data__
1.	Drop data .csv file available [here](https://github.com/Call-for-Code/Al-Wasl.Connect/tree/master/data), select target schema
1.	Kindly use defualt schema that would similar to __RGJ19757__(three letters and 4 digits)
1. Click new __table__, if the .csv file is Transaction.csv give the table name __Transaction__.

   __NOTE__ : When data is loaded. If there is __DATE__ field, please change the Date format: __DD/MM/YYYY__ and Timestamp format:__DD/MM/YYYY H:MM TT__
1.	Once everything is completed click __Begin Load__
1. Follow steps 5-9 for other 4 csv files.


## Backend service:
1.	Backend service is implemented in node.js
1.	Backend server is available [here](https://github.com/Call-for-Code/Al-Wasl.Connect/tree/backend)
1.	Move into the directory and make the changes as below:
    1.	In __manifest.yml__ change name and host field to some unique value.
    1.	Please add __.env__ file with your db2 credentials
1. Then login IBM Cloud Platform from CLI    
1.	Once  above steps are completed,must be in backend directory and pass __cf push 'name of app'__ command to create the IBM Cloud Foundry service.
1. Copy the URL example https://trustdon....eu-gb.mybluemix.net/ that will be used in  __Frontend servie__ step 4.


## Frontend service :
1.	Frontend service is implemented in angular 9
1.	Applicaiton frontend is available [here](https://github.com/Call-for-Code/Al-Wasl.Connect/tree/frontend)
1.	Update __.env__ file with db2 service credentials
1.	Update route in two files:
```bash
Open src folder -> environments (update .ts & .prod files where the backend server is URL running  eg https://trustdon....eu-gb.mybluemix.net/)
 ```
1.	Run __“npm install”__
1.	Run __“yarn install”__
1.	Then build the project __“ng build”__
1.	Now you can see the __“Dist”__ folder , add manifest.yml (keep name unique, available [here](https://github.com/Call-for-Code/Al-Wasl.Connect/tree/frontend))
1.	Push only __Dist__ folder files to your GitHub repositry
1. Need to integrate __IBM Toolchain__ service for Continuous Integration and deployment
1.	Open IBM Account search for Toolchain and select develop a Cloud Foundry app.

***NOTE : Clone the application and push it under your GitHub account and provide the URL. Because pipeline will not trigger if some changes are made in the repository.***

![toolchain](toolchain1.png)

12.	In __Delivery Pipeline__ section , select new -> ok (it will generate a new API)
13.	Once above steps are completed click __Create__.
14.	This toolchain will automatically create a Cloud Foundry app for you go to resources list and check application would be up and running.

## Live demo

You can find a running application at [here](https://al-wasal-connect.eu-gb.mybluemix.net/)

__Credentials__

1. Donor Login
   - Registration # : 1234567890112
   - password : 1234

1. Government Login
    - Username : govt
    - password : admin


## Built with
* [IBM Cloud Foundry](https://cloud.ibm.com/cloudfoundry/overview)
* [IBM Toolchain](https://cloud.ibm.com/devops/create)
* [IBM Cloudant](https://cloud.ibm.com/catalog/services/db2)
* [Node.js](https://nodejs.org/en/)

## Version

v0.1
