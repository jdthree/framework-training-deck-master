# Lab: Generate the Application

## `ionic start`

The first step is to create the application and connect the application to Ionic Pro. To do this you will use the `ionic start` command.

1. at a command prompt, change directory to your working folder
1. type: `ionic start ionic-weather tabs --cordova`

This process will run for a while. It will generate the application from a starter template, set up the application to use Cordova, install the required libraries via NPM, initialize the git repository for the application, and perform the initial git commit.

The output looks like this:

```bash
~/Projects/Training: ionic start ionic-weather tabs --type=angular --cordova
✔ Preparing directory ./ionic-weather - done!
✔ Downloading and extracting tabs starter - done!
> ionic integrations enable cordova --quiet
[INFO] Downloading integration cordova
[INFO] Copying integrations files to project
[OK] Integration cordova added!

Installing dependencies may take several minutes.

     ✨   IONIC  DEVAPP   ✨

 Speed up development with the Ionic DevApp, our fast, on-device testing mobile app

  -  🔑   Test on iOS and Android without Native SDKs
  -  🚀   LiveReload for instant style and JS updates

 -->    Install DevApp: https://bit.ly/ionic-dev-app    <--

────────────────────────────────────────────────────────────

> npm i

>> Snipped NPM output...

> git init
Initialized empty Git repository in /Users/kensodemann/Projects/Training/ionic-weather/.git/

     🔥   IONIC  PRO   🔥

 Supercharge your Ionic development with the Ionic Pro SDK

  -  ⚠️   Track runtime errors in real-time, back to your original TypeScript
  -  📲  Push remote updates and skip the app store queue

 Learn more about Ionic Pro: https://ionicframework.com/pro

────────────────────────────────────────────────────────────

? Install the free Ionic Pro SDK and connect your app? (Y/n) 
```

Note the final message in the output. This is asking you if you would like to connect your application to Ionic Pro. You want to do this.

1. answer 'Y' to the Ionic Pro SDK question
1. you will be asked if you want to link to an existing app or create a new one, choose to create a new one
1. you will be asked if you would like to use GitHub integration or Ionic Pro, choose Ionic Pro

Your application will have been generated and you should see the following instructions:

```bash
[INFO] Next Steps:
       
       - Go to your newly created project: cd ./ionic-weather
       - Get Ionic DevApp for easy device testing: https://bit.ly/ionic-dev-app
       - Finish setting up Ionic Pro Error Monitoring: 
       https://ionicframework.com/docs/pro/monitoring/#getting-started
       - Finally, push your code to Ionic Pro to perform real-time updates, and 
       more: git push ionic master
```

## Remote Repositories

Once you have ype the following command: `git remote -vv`. You should see something like this:

```bash
~/Projects/Training/ionic-weather (master): git remote -vv
ionic	git@git.ionicjs.com:kensodemannionic/ionic-weather.git (fetch)
ionic	git@git.ionicjs.com:kensodemannionic/ionic-weather.git (push)
```

This is the remote where you push changes that you want Ionic Pro to build and deploy. You should not use this as your main remote repository. For that, you should either use a cloud based git service such as GitHub or Bitbucket or use an in-house solution such as Bitbucket Enterprise. For this course, let's use one of the public cloud based services. I will use GitHub, but the process is similar for others.

1. log on to GitHub
1. click the "New" button
1. give the repository a name like `ioinc-weather`
1. keep it public
1. click "Create repository"
1. `git remote add origin git@github.com:kensodemann/ionic-weather.git`
1. `git push -u origin master`

Now `git remote -vv` will show two remote repositories:

```bash
~/Projects/Training/ionic-weather (master): git remote -vv
ionic	git@git.ionicjs.com:kensodemannionic/ionic-weather.git (fetch)
ionic	git@git.ionicjs.com:kensodemannionic/ionic-weather.git (push)
origin	git@git.github.com:kensodemannionic/ionic-weather.git (fetch)
origin	git@git.github.com:kensodemannionic/ionic-weather.git (push)
```

The `origin` remote is meant to be the source of truth for your project. This is where all developers will `pull` changes from and will `push` changes to.

The `ionic` remote is meant to be pushed to when an Ionic Pro build is desired and will typically be pushed to by a smaller set of developers depending on how your project is managed.

## Building and Running

Let's just make sure you can build your application:

1. `cd ionic-weather`
1. `ionic serve`

You should now see your application running in your default browser.