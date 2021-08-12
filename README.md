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

