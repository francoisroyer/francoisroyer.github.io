# Setup for local development

cd ~/Github/francoisroyer/francoisroyer.github.io
mkdir master dev
cd master
git clone git@github.com:francoisroyer/francoisroyer.github.io.git .
git branch -d dev
#make sure ./build is listed in .gitignore

cd ../dev
git clone git@github.com:francoisroyer/francoisroyer.github.io.git .
git checkout -b dev
git branch -d master

cd ../dev
cactus build
cp -R .build/ ../master
cd ../master
git add .
git commit -m "publishing"
git push origin master
