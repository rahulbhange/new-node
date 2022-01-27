# new-node
1. As per our disscusion in this project i have tried to put some efforts please find the above.
  a. In package.json file of this node app i used sonar scanner for code review.
  b. nexus registry is added to package.json file .
  c. For authentication with my nexus server i added .npmrc file in which i have added my nexus credential in base64 for encryption.

2. After that i created Dockerfile which we will be using to deploy onto our kubernetes cluster.

3. In jenkinsfile i have created the cicd pipeline. this script start from git checkout to npm start.
  a. step 1: gitcheckout
  b. step 2: npm install
  c. step 3: npm run sonar
  d. step 4: npm publish
  e. step 5: npm start
  f. step 6: docker build -t .
  g. step 7: docker tag node-js rahul1525/node-js-v1 (note: in jenkins we can use jenkins variables for versioning)
  h. step 8: docker push node-js-v1


4. In k8s section we can use cert manager for ssl certificate.

5. we can still imrove this infrastructure in future by installing prometheus and grafana for metric base monitoring.
