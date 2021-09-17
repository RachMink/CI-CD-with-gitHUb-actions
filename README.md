# Creating and deploying a React app with gitHub Actions and nginx

For this project I created a react app in VS code and pushed all the appropriate files and folders to my gitHub repository. I then use gitHub actions to create a workflow that continuosly builds the React app when any chages are pushed to the repository. 

#### My workflow

Within gitHub actions I choose the Node.js workflow which creates a YAML file.

`name:` This workflow is called Node.js

`on:` tells github when to trigger the job, which in this case is when the user `push`es to the `main` branch<br>

`jobs:` this is what is ran every time something is pushed to the main branch<br>

This job is a `build` <br>

`runs-on:` specifies where this runs on - in our case `self-hosted` - virtual private server which I have set up through Settings > Actions > Runners > Add Runner <br>

`node-version:` runs all the jobs for version 16 of Node.js <br>

`steps:` what we want the script to run <br>

`run npm i` i stands for install. After all depedencies are installed, we run the build <br>

`run npm build --if-present ` run the build if the script is present<br>

`run npm test` runs all the test cases <br>

## Using my Action

This action will run any time I push something into my repository. 

Therefore, right after I updated my README.md or my node.js.yml and commit the changes to the master branch - my action begins to run. 

While the action runs we can navigate to the action tab where we can see a list of all my workflows, since I only have one workflow realted to this project I navigate to the Node.js CI workflow (which I named in node.js.yml) 

<img width="1116" alt="Screen Shot 2021-08-12 at 3 01 01 PM" src="https://user-images.githubusercontent.com/82296790/129253585-1c216dc8-a9de-469b-90fa-e369fc3c7083.png">

Once there I can choose any workflow run to track.

I choose the in-progress run and click on it to see the summary of the job. 

<img width="1128" alt="Screen Shot 2021-08-12 at 2 57 59 PM" src="https://user-images.githubusercontent.com/82296790/129253198-450517b0-e500-44c2-9dcb-5a9692a97eaa.png">

We can click on the summary to see a more in depth break down of what is happening in real time
<img width="1117" alt="Screen Shot 2021-08-12 at 2 47 11 PM" src="https://user-images.githubusercontent.com/82296790/129251753-4c13453c-d00d-43eb-88cd-fd4f8a14337b.png">

This shows the first step of the build which declares my runner to be the one I set up previously
<img width="1116" alt="Screen Shot 2021-08-12 at 2 52 04 PM" src="https://user-images.githubusercontent.com/82296790/129252419-aa5a0ba4-eda0-438e-a97d-767458496be9.png">

Once each job is completed successfully we will see a green check next to the build 
<img width="1109" alt="Screen Shot 2021-08-12 at 2 46 16 PM" src="https://user-images.githubusercontent.com/82296790/129251636-6e397fa3-6618-445a-b985-55cb1e29860d.png">

Now, in order to view my app deployed on the web I use Nginx which is a web server already installed on my mac and change the root to see my edits in the server. 

<img width="1082" alt="Screen Shot 2021-08-12 at 5 03 46 PM" src="https://user-images.githubusercontent.com/82296790/129269569-bab0a0bc-f996-46cc-9cda-5c53729f0979.png">


#### Sources Used
 - https://lab.github.com/githubtraining/github-actions:-hello-world 
 - https://www.youtube.com/watch?v=X3F3El_yvFg&t=186s
 - https://medium.com/@bulutto/create-your-github-page-with-github-actions-to-continuously-integrate-and-deploy-aff668c18dfb
 - https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions#jobsjob_idruns-on
 - https://docs.github.com/en/actions/guides/building-and-testing-nodejs
 - https://reactjs.org/docs/create-a-new-react-app.html

