# Creating and deploying a React app

For this project I created a react app in VS code and pushed all the appropriate files and folders to my gitHub repository. I then use gitHub actions to create a workflow and deploy the React app. 

Within gitHub actions I choose the Node.js workflow which creates a YAML file. 

`name`


`on:` tells github when to trigger the job, which in this case is when the user `push` to the `main` branch
`jobs:` this is what is run every time something is pushed to the main branch
`build:` 

`runs-on:` specifies where this runs on - in our case `self-hosted` - virtual private server
`node-version:` runs all the jobs for every version of Node.js

`steps:` what we want the script to run
`run npm i` i stands for install, 
after all depedencies are installed, we run the build 
`run npm build --if-present ` run the build if the script is present

`run npm test` runs all the test cases 

Therefore, right after I updated my README.md and commited the changes to the master branch - my action begins to run. If we go into the action tab we can see a summary of the job and more in depth of what is being ran when. 
<img width="1124" alt="Screen Shot 2021-08-12 at 2 28 31 PM" src="https://user-images.githubusercontent.com/82296790/129249501-dd5238be-6a1e-4df0-b8b2-e6f30faeca66.png">

And they slowly complete one by one.
<img width="1119" alt="Screen Shot 2021-08-12 at 2 29 57 PM" src="https://user-images.githubusercontent.com/82296790/129249707-76456a61-f7a6-45d0-a319-a864eeb0cba3.png">

Once each job is completed successfully we can see a green check next to every build 
<img width="1120" alt="Screen Shot 2021-08-12 at 2 30 41 PM" src="https://user-images.githubusercontent.com/82296790/129249801-8ea1798d-3a01-4004-a730-d9de5f185911.png">
