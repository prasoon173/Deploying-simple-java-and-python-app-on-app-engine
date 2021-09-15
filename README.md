# Deploying-simple-java-and-python-app-on-app-engine
Here I have deployed java and python app on two different services of app engine. Later on using build trigger, automated the deployment.

Initially, I wrote main.py, requirements.txt, myserviceone.yaml file and checked this python app locally on port 8080
      $python3 -m venv env
      $source env/bin/activate
      $cd YOUR_SAMPLE_CODE_DIR
      $pip install -r requirements.txt
      http://localhost:8080 ( on brwoser ) else view port 8080 on cloud shell
Once that works fine, I deployed it to app engine using $gcloud app deploy myserviceone.yaml

Secondly, I wrote app.js, package.json, myservicetwo.yaml file and then checked this java app locally on port 8080 
      $npm install
      $npm start
Then, I deployed it to app engine as third service i.e myservicetwo using $gcloud app deploy myservicetwo.yaml

Once all these were done. I pushed all my files to my source repo. and then wrote cloudbuild.yaml file. Hence, created a build trigger using cloud build. 
Came back to my main.py and app.js file and then did some change in code. Pused it again to repo, Based on which, build triggered and it deployed another version of apps on respective services running on app engine. 
