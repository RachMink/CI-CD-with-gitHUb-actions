# Creating and deploying a React app

For this project I created a react app in VS code and pushed all the appropriate files and folders to my gitHub repository. I then use gitHub actions to create a workflow and deploy the React app. 

Within gitHub actions I choose the Node.js workflow which creates a YAML file. 

`name`


`on:` tells github when to trigger the job, which in this case is when the user `push` to the `main` branch
`jobs:` this is what is run every time something is pushed to the main branch
`build:` 

`runs-on:` specifies where this runs on - in our case `self-hosted`
