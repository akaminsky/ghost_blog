## How to deploy to github pages 

## Install Buster
pip install buster (to install buster)
brew install wget (required by buster)

## Setup Ghost locally
- Download Ghost
- Unzip and go to the directory
- npm install
- npm start to run Ghost locally
- Visit http://127.0.0.1:2368/ghost to create an admin account and setup Ghost locally
- I then loaded my custom theme to content/themes subfolder in the Ghost installation (you need to restart Ghost locally to see the new theme under the settings)
- Create your articles and make changes to the theme as needed and test everything locally

## Create GitHub Pages repo & set up Buster
- Go to your GitHub account and create a public repo named accountname.github.io (in my case it was ledtechnica.github.io)
- I switched to a different folder from the Ghost installation to keep the generated static files separately
- From the selected folder run buster setup and enter the repo address you just created when prompted (e.g. https://github.com/ledtechnica/ledtechnica.github.io.git)
- Once this is done, run buster generate --domain=http://127.0.0.1:2368 which will generate all the needed files under the static subfolder created in the previous step.
- cd static to switch into static subfolder, git add -all and then git commit -m 'Initial commit' followed by a git push to upload your repo to GitHub.
- GitHub Pages indicate that you might need to wait for up to 10 minutes to see your repo but in my case it took around 20 minutes. So if you are the impatient type like me, you might need to do a bunch of refreshes to finally see your blog.

## Custom Domain
- Create a file named CNAME in the static folder and include your custom domain name in it - e.g. ledtechnica.com
- Commit and push the changes to GitHub and don't forget to update your DNS records.
- Please note it also takes some time for the GitHub Pages to show your site under the custom domain name.