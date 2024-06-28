# 🚀 Getting started with Strapi (API Deployment on AWS )

Strapi comes with a full featured [Command Line Interface](https://docs.strapi.io/dev-docs/cli) (CLI) which lets you scaffold and manage your project in seconds.

 🌠𝐅𝐨𝐫𝐤 𝐭𝐡𝐢𝐬 𝐑𝐞𝐩𝐨 𝐚𝐧𝐝 𝐌𝐚𝐫𝐤 𝐚𝐬 𝐒𝐭𝐚𝐫 🌟 

 🔗(https://github.com/VyankateshwarTaikar/strapi2_product.git)
 

## Prerequisites to Install Strapi
2 GB of RAM (The more, the better performance)

2 vCore CPU (Recommended in the documentation)

t3.small (instance)

Minimum of 30 GB or more Disk Space

Ubuntu 20.04

![image](https://github.com/VyankateshwarTaikar/strapi/assets/102132721/cd4f9546-5916-43b9-b1c2-ed30605da93a) 

# 🌠Install required dependancy as the 

## Note: You have to use npm or yarn . Any one should be installed on the server enviroment to run strapi.

sudo apt update

sudo apt install -y curl gnupg2 build-essential 

## Install Node.js:
## 1.installs nvm (Node Version Manager)
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
## 2.download and install Node.js (you may need to restart the terminal)

sudo reboot

nvm install 20

curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash -

sudo apt install -y nodejs

## If npm is not the correct version, upgrade it:

sudo npm install -g npm@10.7.0

npm -v  # Should return 10.7.0


## Install Yarn:
sudo apt install curl 

![image](https://github.com/VyankateshwarTaikar/strapi/assets/102132721/14824006-3941-4da0-996d-28ba65eec59d)  

curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add - 

echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list

sudo apt update

sudo apt install -y yarn     (optional)

## Verify the installation:
yarn -v  # Should return 1.22.22      (optional)

## 👉 Checking Versions

node -v  # Should return v20.14.0

npm -v   # Should return 10.7.0

yarn -v  # Should return 1.22.22      (optional)

![image](https://github.com/VyankateshwarTaikar/strapi/assets/102132721/e2badbe1-9231-4bf5-8b9d-6218254f7264) 

# 🌟Install Strapi 

## 1.Once the environment is complete, use the following instructions to begin installing Strapi and creating your first website:

sudo npm install strapi@alpha -g
 
sudo npm install pm2 -g 

## 2.Next, make a new Strapi folder/project and provide any name.

cd ~

npx -y create-strapi-app strapi --quickstart 


# Start and Stop with Strapi

## Firstly, you have to change the code from Package.json
```

# CODE Start ============ >>>>>
{
  "name": "strapi",
  "private": true,
  "version": "0.1.0",
  "description": "A Strapi application",
  "scripts": {
    "develop": "strapi develop",
    "start": "strapi start",
    "build": "strapi build",
    "strapi": "strapi",
    "deploy": "strapi deploy",
    "stop": "kill $(lsof -t -i:1337)"
  },
  "devDependencies": {},
  "dependencies": {
    "@strapi/strapi": "4.25.1",
    "@strapi/plugin-users-permissions": "4.25.1",
    "@strapi/plugin-i18n": "4.25.1",
    "@strapi/plugin-cloud": "4.25.1",
    "better-sqlite3": "8.6.0",
    "react": "^18.0.0",
    "react-dom": "^18.0.0",
    "react-router-dom": "5.3.4",
    "styled-components": "5.3.3"
  },
  "author": {
    "name": "A Strapi developer"
  },
  "strapi": {
    "uuid": "705fbe27-9229-4b8b-ace3-8e0337e03795"
  },
  "engines": {
    "node": ">=18.0.0 <=20.x.x",
    "npm": ">=6.0.0"
  },
  "license": "MIT"
}
# <<<<<  Code End ============

```


🔑Go to the inside  dircetory for for your project to start , stop & restart strapi  👉ex: here is the strapi 

npm run start    (To start the Npm)

npm run stop  (To stop the Npm)

npm run restart   (To Restart the Npm)
 

![image](https://github.com/VyankateshwarTaikar/strapi/assets/102132721/2bb4b416-9524-4f66-9449-55469f49ff51)![image](https://github.com/VyankateshwarTaikar/strapi/assets/102132721/2bb4b416-9524-4f66-9449-55469f49ff51)

press Y

![image](https://github.com/VyankateshwarTaikar/strapi/assets/102132721/051a8f80-0981-49c5-abf1-aa1be9759916) 


choose 𝐬𝐤𝐢𝐩 and processed for the manual installation 



## note: 👇 If you are already done with installation then you can run where the project is crearted or project is stopped ( Not Recommeded in Production Enviroment )

inside project diretory run command 

pm2 start yarn --name strapi -- develop        

![image](https://github.com/VyankateshwarTaikar/strapi/assets/102132721/caee8978-5b4e-48df-b876-2606e278ee91)

## Now you can accessed by manually 

http://localhost:1337/admin 

or 

http://public_ip_of_instance:1337/admin

example : http://16.171.110.197:1337/admin


![Screenshot_3](https://github.com/VyankateshwarTaikar/strapi/assets/102132721/1c8f1f3b-5487-46be-b399-d7c0f519aed9) 


So, now you done with manual deployment for strapi 

# cicd for 

## install git on server 
sudo apt update

sudo apt install git

## set up your Git username and email: 

git config --global user.name "Your Name"

git config --global user.email "your-email@example.com"

## Initialize a Git Repository
cd strapi
git init


## Add Remote Repository
git remote add origin [https://github.com/USERNAME/REPOSITORY.git](https://github.com/VyankateshwarTaikar/strapi.git)

## Add Files and Commit

git add .
git commit -m "Strapi API deploy on AWS"

## Push Code to GitHub
git push -u origin main

## When you push your code, use your GitHub username and the generated token as the password. For example:
Username for 'https://github.com': your-username
Password for 'https://your-username@github.com': your-token


Creating a Personal Access Token (PAT) & put it as as a password (your_token).

-------------------------------------------------
# Implement CI/CD using GitHub Actions. 

master.yml

```

name: CI/CD for Strapi
on:
  push:
    branches:
      - master
  pull_request:
    branches:
      - master
jobs:
  ci:
    name: Continuous Integration
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v2
      - name: Set up Node.js
        uses: actions/setup-node@v2
        with:
          node-version: '20'  # Adjust the Node.js version 
      - name: Install dependencies
        run: |
          npm install
      - name: Build Strapi application
        run: |
          npm run build
  cd:
    name: Continuous Deployment
    runs-on: ubuntu-latest
    needs: ci
    steps:
      - name: Checkout code
        uses: actions/checkout@v2
      - name: SSH commands setup
        uses: appleboy/ssh-action@master   #github action marketplace 
        with:
          host: ${{ secrets.SERVER_HOST }}
          username: ${{ secrets.SERVER_USER }}
          key: ${{ secrets.SERVER_KEY }}
          script: |
            cd ~/strapi
            git pull origin master
            npm install
            npm run build
            pm2 stop strapi || true
            nohup npm start > strapi.log 2>&1 &   
            
            # no hang up(process to continue running even after the user has logged out),
            #2>&1: This part redirects the standard error (stderr) to the same location as the standard output (stdout). 
            #In this case, both stdout and stderr are written to strapi.log.  & means process run in backgound

```


------------------------------------------------------------------

After you made a changes it will automatically starts build and deploy 

![image](https://github.com/VyankateshwarTaikar/strapi/assets/102132721/110a99c6-f043-4c65-a59a-cce7d7ca6344) 

![image](https://github.com/VyankateshwarTaikar/strapi/assets/102132721/1d2355c3-67d5-42f0-a21c-5493b46d8086) 

--------------------------------------------------------------------------------------------------

 🌠𝐅𝐨𝐫𝐤 𝐭𝐡𝐢𝐬 𝐑𝐞𝐩𝐨 𝐚𝐧𝐝 𝐌𝐚𝐫𝐤 𝐚𝐬 𝐒𝐭𝐚𝐫 🌟 

 🔗 https://github.com/VyankateshwarTaikar/strapi2_product.git
