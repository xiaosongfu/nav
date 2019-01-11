### firebase cli 工具

> 安装

```
Last login: Wed Jan  9 11:38:26 on ttys000
fuxiaosongdeMac-mini:~ fuxiaosong$ npm install -g firebase-tools
/Users/fuxiaosong/.nvm/versions/node/v6.14.1/bin/firebase -> /Users/fuxiaosong/.nvm/versions/node/v6.14.1/lib/node_modules/firebase-tools/lib/bin/firebase.js

......

```

> 登录

```
fuxiaosongdeMac-mini:dart fuxiaosong$ export http_proxy=http://127.0.0.1:1087;export https_proxy=http://127.0.0.1:1087;
fuxiaosongdeMac-mini:dart fuxiaosong$ firebase login
? Allow Firebase to collect anonymous CLI usage and error reporting information? Yes

Visit this URL on any device to log in:
https://accounts.google.com/o/oauth2/auth?client_id=563584335869-fgrhgmd47bqnekij5i8b5pr03ho849e6.apps.googleusercontent.com&scope=email%20openid%20https%3A%2F%2Fwww.googleapis.com%2Fauth%2Fcloudplatformprojects.readonly%20https%3A%2F%2Fwww.googleapis.com%2Fauth%2Ffirebase%20https%3A%2F%2Fwww.googleapis.com%2Fauth%2Fcloud-platform&response_type=code&state=861964990&redirect_uri=http%3A%2F%2Flocalhost%3A9008

Waiting for authentication...

✔  Success! Logged in as xiaosfu@gmail.com
fuxiaosongdeMac-mini:dart fuxiaosong$
```

> 初始化项目

```
fuxiaosongdeMac-mini:api fuxiaosong$ firebase init

     ######## #### ########  ######## ########     ###     ######  ########
     ##        ##  ##     ## ##       ##     ##  ##   ##  ##       ##
     ######    ##  ########  ######   ########  #########  ######  ######
     ##        ##  ##    ##  ##       ##     ## ##     ##       ## ##
     ##       #### ##     ## ######## ########  ##     ##  ######  ########

You're about to initialize a Firebase project in this directory:

  /Users/fuxiaosong/dev/sdk/dart/docs/2.1.0/api

? Which Firebase CLI features do you want to setup for this folder? Press Space to select features, then Enter to confirm your choices. Hosting: Confi
gure and deploy Firebase Hosting sites

=== Project Setup

First, let's associate this project directory with a Firebase project.
You can create multiple project aliases by running firebase use --add,
but for now we'll just set up a default project.

? Select a default Firebase project for this directory: [create a new project]

=== Hosting Setup

Your public directory is the folder (relative to your project directory) that
will contain Hosting assets to be uploaded with firebase deploy. If you
have a build process for your assets, use your build's output directory.

? What do you want to use as your public directory? ./
? Configure as a single-page app (rewrite all urls to /index.html)? No
✔  Wrote .//404.html
? File .//index.html already exists. Overwrite? No
i  Skipping write of .//index.html

i  Writing configuration info to firebase.json...
i  Writing project information to .firebaserc...
i  Writing gitignore file to .gitignore...

✔  Firebase initialization complete!

Project creation is only available from the Firebase Console
Please visit https://console.firebase.google.com to create a new project, then run firebase use --add
fuxiaosongdeMac-mini:api fuxiaosong$ firebase use --add dart-api-54eec
Now using project dart-api-54eec
fuxiaosongdeMac-mini:api fuxiaosong$
```

> 本地预览

```
firebase serve
```

> 部署项目

```
fuxiaosongdeMac-mini:api fuxiaosong$ firebase deploy

=== Deploying to 'dart-api-54eec'...

i  deploying hosting
i  hosting[dart-api-54eec]: beginning deploy...
i  hosting[dart-api-54eec]: found 12696 files in ./
⠋  hosting: hashing files [4179/12696] (32%)

......
```

或者

```
firebase deploy --project dart-api-54eec
```

> 在线浏览

```
firebase open
```

或通过浏览器打开 url 查看。