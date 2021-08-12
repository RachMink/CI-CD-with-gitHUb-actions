# Creating and deploying a React app

For this project I created a react app in VS code and pushed all the appropriate files and folders to my gitHub repository. I then use gitHub actions to create a workflow and deploy the React app. 

Within gitHub actions I choose the Node.js workflow which creates a YAML file. 

`name:` This is called Node.js 


`on:` tells github when to trigger the job, which in this case is when the user `push`es to the `main` branch<br>

`jobs:` this is what is run every time something is pushed to the main branch<br>

`runs-on:` specifies where this runs on - in our case `self-hosted` - virtual private server which I have set up through Settings > Actions > Runners > Add Runner <br>

`node-version:` runs all the jobs for version 16 of Node.js <br>

`steps:` what we want the script to run <br>

`run npm i` i stands for install. After all depedencies are installed, we run the build <br>

`run npm build --if-present ` run the build if the script is present<br>

`run npm test` runs all the test cases <br>

## Using my Action

This action will run any time I push something into my repository. 

Therefore, right after I updated my node.js.yml and commit the changes to the master branch - my action begins to run. 

While the ation runs we can navigate to the action tab where we can see a summary of the job and if we look around we can see a breakdown of what is being ran - in real time.

<img width="1124" alt="Screen Shot 2021-08-12 at 2 28 31 PM" src="https://user-images.githubusercontent.com/82296790/129249501-dd5238be-6a1e-4df0-b8b2-e6f30faeca66.png">

Once each job is completed successfully we can see a green check next to the build 
<img width="1109" alt="Screen Shot 2021-08-12 at 2 46 16 PM" src="https://user-images.githubusercontent.com/82296790/129251636-6e397fa3-6618-445a-b985-55cb1e29860d.png">

<img width="1117" alt="Screen Shot 2021-08-12 at 2 47 11 PM" src="https://user-images.githubusercontent.com/82296790/129251753-4c13453c-d00d-43eb-88cd-fd4f8a14337b.png">

This screenshot shows the first step of the build which declares my runner to be the one I set up in previously
<img width="1116" alt="Screen Shot 2021-08-12 at 2 52 04 PM" src="https://user-images.githubusercontent.com/82296790/129252419-aa5a0ba4-eda0-438e-a97d-767458496be9.png">
