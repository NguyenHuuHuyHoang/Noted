1 - Tạo project trên trang firebase.
2 - firebase init trong project muốn deploy
3 - chọn hosting
4 - setting hosting
5 - thêm thư mục vào public firebase
6 - firebase deploy

==Deploy từ Github project==
- Apps are developed on local developer machines
- Pushed to GitHub
- Travis CI deploys the app to Firebase Hosting from GitHub
- Requirment: 
	- I assume that you have:
	- Basic understanding of Firebase
	- Installed node
	- Installed firebase tools
	- Installed Git
==Bước 1==
	- Login to GitHub -> Create a new repository
	- Open command prompt, Navigate to your working directory. cd yourdirectory
	- clone the repository to the directory. git clone repositoryname.git
==Bước 2==
	- Login to Firebase, Go to Firebase console
	- Add a new project
	- come back to the command line
	- Login to your account. firebase login
	- Initialise firebase app. firebase init
	- choose a project, type yes to install the dependencies -> continue
	- To integrate with Travis CI, we would need Firebase token.
	- Type in command line. firebase login:ci
	- This will open up a browser to sign in once more
	- Copy the token, we will need this for Travis CI. 
	- Create .travis.yml file in the root of the project, and paste the following in file
	- Make sure you replace projectId with the actual projectId, which can be found in the firebase console
	- projectId can be found in Firebase console.
==Bước 3==
	- Login to travis-ci.org
	- Click on signin with GitHub
	- Click on "+" sign next to my repositories
	- All the GitHub projects will be listed
	- If not visible click on "Sync Account"
	- Next to the Repository name click on "x" button to flip the switch
	- Now click the gear icon before the repository.
	- Under "Environment Variables" add "FIREBASE_TOKEN" and the previously generated token via firebase login:ci. This will help Travis CI to deploy to Firebase Hosting.
	- Come back to command line, and do a git push to the GitHub repo.
	- git add .
	- git commit -m 'commit message'
	- git push origin master
	After these three the code gets pushed to GitHub, from there Travis CI starts the process, Ideally you would run the tests in Travis CI, for simplicity of the setup, there are no running tests.