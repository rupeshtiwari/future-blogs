---
title: Getting Started with Monorepo with Nx Nrwl
date: 2021-11-19 00:00 +0000
description: 'Create Monorepo using Nx with angular projects and applications'
author_profile: true
published: true
read_time: true
comments: true
share: true
related: true
toc: true
toc_sticky: true
image: https://i.imgur.com/qxXxmBa.png
header:
  image: https://i.imgur.com/zipiW93.png
  teaser: https://i.imgur.com/qxXxmBa.png
  og_image: https://i.imgur.com/qxXxmBa.png
tags:
  - webdev
  - tutorial
  - beginners
  - javascript
---

In this article, I will walk you through the steps to create one [nx monorepo](https://nx.dev/) workspace with Angular application and libraries from empty preset.

1. We will use pipeline caching to improve build speed.
2. We will publish our application to npm.

## Requirements for my monorepo

1. I need **Karma** test runner
2. I **don't need e2e test** for applications
3. I want my **applications to be publishable**
4. I want my **libraries to be not publishable**
5. Create **Azure CI/CD pipelines**
6. Deploy **Application to NPM registry**

## Environment Requirement

Make sure you have node.js installed which is greater than V10. I have installed node.js v14.

I am using Vs Code and installed nx console vs extension to get inbuilt way of creating apps/libs from nx console only.

Make sure you have installed [Nx Console](https://nx.dev/latest/angular/getting-started/console) in your vs code.
![](https://i.imgur.com/gWKa76u.png =250x200)

## Nx Monorepo Default Test Runner is JEST

When you create nx monorepo with `Angular` or `React` or `Next.js` or `Gatsby` or `next.js` or `Web Components` then it will give you `JEST` as unit test runner. In case you want to get `karma` test runner then you have to create Empty workspace and then add `@nrwl/angular` latter then add new application or lib with karma unit test runner.

## Default Workspace structure

In order to create workspace We run below script

`npx create-nx-workspace@latest`

Give workspace name: myorg

Select Layout: I select Angular Application (A workspace with a single Angular Application)

Application Name: cutepuppies-admin

Stylesheet Format: SASS

Linter: TSLINT

Nx Cloud: No ( this is default )

![](https://i.imgur.com/iMK98Jr.png){: .full}

It will create the workspace with angular app that we defined.

![](https://i.imgur.com/X8fvsUc.png){: .full}

When you will use their template they will add end to end test for application. They will also add jest test runner.

![](https://i.imgur.com/GLOkklz.png){: .full}

In my workspace I do not want Jest and I do not want e2e tests. So I am deciding to again create my workspace with empty preset.

## Creating new NX Monorepo workspace

1.  Run `npx create-nx-workspace@latest`

2.  Give organization name: `curise`

3.  Select angular application for the workspace. `angular`

This will install `@nrwl/angular` plugin to give you tools to create angular lib and apps.

![](https://i.imgur.com/zia6hBU.png){: .full}

4.  Then enter angular application name: admin

![](https://i.imgur.com/jn9PH3x.png){: .full}

5.  Next select Style format as SASS
6.  Default Linter: Choose TSLINT since I have angular app
7.  Nx Cloud give caching over cloud: No ( it needs paid subscription plan)

![](https://i.imgur.com/8XevXrP.png){: .full}

Run the script:
![](https://i.imgur.com/roU0Y90.png){: .full}

## Understanding NX Monorepo Workspace

![](https://i.imgur.com/bNRYcQI.png){: .full}

1. **Apps**
2. **libs**
3. **tools**
   Tools folder has tsconfig file that means u can write typescript files and compile them in JS.
4. **decorate-angular-cli.js**
5. **jest.preset.js**
6. **angular.json**
   It create angular.json file to manage your workspace. However, if you want to create empty monorepo project then it creates **workspace.json** file.

## Building Project

Run `nx build`

![](https://i.imgur.com/Pig0oei.png){: .full}

Showing `dist` folder.

![](https://i.imgur.com/wIjX2a2.png){: .full}

## Empty Nx Monorepo Advantage and Disadvantages

After creating empty workspace.

**Benefits of Empty Workspace**

1. You can use `karma` unit test runner
2. You can use `workspace.json` to configure any apps and libs.

**Disadvantages of empty workspace**:

1. You have to write the angular cli decorator for `Nx CLI`

Regardless of empty or pre-populated workspace you must create your own `CI/CD` Pipelines and Nx commands for your pipelines.

## Creating new Empty Nx Monorepo workspace

Create desired working folder and from that location open `powershell` on windows machine I found working on `git bash commands` were not working nicely.

Run below script to create empty workspace

`npx create-nx-workspace@latest --preset=empty`

Above script will ask you

1. organization name and
2. Want to use Nx Cloud or not.

![](https://i.imgur.com/2nPySWd.png){: .full}

Notice it created the workspace

![](https://i.imgur.com/ApKE767.png){: .full}

So Now I get empty app and library folders.

![](https://i.imgur.com/vl5KtTa.png){: .full}

This is my dependencies that I get in package.json

![](https://i.imgur.com/Y4qQNIe.png){: .full}

## What NX CLI does?

`Nx CLI` commands will invoke `Angular CLI`. The `Nx CLI` simply does some optimizations before invoking the `Angular CLI`. `Nx Cli` can execute all of the `ng cli` commands. The benefit you get with `Nx CLI` is **Computation Caching** which gives faster execution of tasks. Also Nx CLI is technology agnostic You can use `Nx CLI` to run `angular`, `react`, `JavaScript` or any project scripts.
So it gives uniformity in your team to always run `Nx CLI` in your workspace regardless of any front-end technology you are using..

## Using Nx CLI over Angular CLI

In order to point `ng cli` to `Nx CLI` we have to run **decorate-angular-cli.js** file. Because of `symlinking` you can still type `ng build` or `ng test` or `ng lint` in the terminal. The ng command, in this case, will point to nx, which will perform optimizations before invoking `ng`.

After install we can execute this decorator file.

```json
"postinstall": "node ./decorate-angular-cli.js && ngcc --properties es2015 browser module main --first-only --create-ivy-entry-points",
```

## How to opt out of NX CLI

Although I don't recommend this option :-1:  
However, in case you want to opt out of `NX CLI` then follow below steps:

1.  Replace occurrences of nx with ng in your package.json
2.  Remove the script from your postinstall script in your package.json
3.  Delete and reinstall your node_modules

## Understanding NX Workspace Scripts

```json=
"scripts": {
    "nx": "nx",
    "start": "nx serve",
    "build": "nx build",
    "test": "nx test",
    "lint": "nx workspace-lint && nx lint",
    "e2e": "nx e2e",
    "affected:apps": "nx affected:apps",
    "affected:libs": "nx affected:libs",
    "affected:build": "nx affected:build",
    "affected:e2e": "nx affected:e2e",
    "affected:test": "nx affected:test",
    "affected:lint": "nx affected:lint",
    "affected:dep-graph": "nx affected:dep-graph",
    "affected": "nx affected",
    "format": "nx format:write",
    "format:write": "nx format:write",
    "format:check": "nx format:check",
    "update": "nx migrate latest",
    "workspace-generator": "nx workspace-generator",
    "dep-graph": "nx dep-graph",
    "help": "nx help"
  },
```

## Creating Angular Library using Nx Console

I will use `nx console` to create application.

Since I want to create Angular applications and libraries I need `@nrwl/angular` node package to be
installed.

please run below script to install `@nrwl/angular`

`npm i -D @nrwl/angular`

![](https://i.imgur.com/uq8rqan.png){: .full}

Select Nx, then select generate and then select Angular Library.

![](https://i.imgur.com/NzsCaoS.png){: .full}

Fill out the required fields. I want to create logger angular library under lib/branding folder with karma testing framework.

![](https://i.imgur.com/rNAerhj.png){: .full}

This is my dry run result

![](https://i.imgur.com/Erh9MXZ.png){: .full}

Logger project is created successfully.
![](https://i.imgur.com/OM0IQE3.png){: .full}

## How to stop dryRun while using Nx Console?

Currently there is no way you can stop dry run therefore, use the script to create application or lib.

```shell
nx generate @nrwl/angular:library --name=utils --directory=branding --importPath=@myor/branding-utils --prefix=myorg-branding-utils --tags=scope:branding,type:branding-utils --no-interactive --dry-run
```

## Creating JS project using NX Console

NX Monorepo only support `JEST` or `NONE` unit test runner for Javascript project.

```shell
nx generate @nrwl/workspace:library --name=ckeditor5 --directory=branding --importPath=@myorg/branding-ckeditor5 --prefix=myorg-branding-ckeditor5 --tags=scope:branding,type:branding-ckeditor5 --no-interactive --js --unitTestRunner=none --dry-run
```

## How to create Run Command in NX Monorepo

Nx Run Command helps to create custom commands

![](https://i.imgur.com/6OPfuS6.png){: .full}

**Target Name** : Bane of the target like `build`
**Project Name** : is the name of the project in the workspace.json file : `branding-ckeditor`

**Command**: `npm run build`

**cwd** location of the src folder of the project

**outputs** where the build artifacts will be stored.
![](https://i.imgur.com/BS0ulgd.png){: .full}

```shell
nx generate @nrwl/workspace:run-commands --name=build --command='npm run build' --project=branding-ckeditor5 --cwd=libs/branding/ckeditor5/src --outputs=libs/branding/ckeditor5 --no-interactive --dry-run
```

This will update the `workspace.json` and `nx.json`

![](https://i.imgur.com/JYPutPu.png){: .full}

Now you can run `nx build branding-ckeditor5`

## Step: Create Angular App using Nx Console

Let's select an angular application this time to create cutepuppies-admin apps.
![](https://i.imgur.com/XRG6STh.png){: .full}

Name: cutepuppies-admin
![](https://i.imgur.com/QNPMMpp.png){: .full}

e2eTestRunner: none ( I don't want this test )
![](https://i.imgur.com/FzeuvBR.png){: .full}

Routing: Generates a routing module select this.

![](https://i.imgur.com/oW0DuLZ.png){: .full}

Tags: scope:itops,type:itops-cutepuppies-admin
Unit Test Runner: Karma
![](https://i.imgur.com/x75qAxN.png){: .full}

Click on the Run button and finally select SASS while it is asking for which style format.
See my app is created
![](https://i.imgur.com/fAz1Q1y.png){: .full}

## Adding Nx CLI Decorator for Nx Empty Workspace

## Step : Let's Create Logging Service & Tests

Let's create a loggingService inside our logger project.
Use Nx Console to create angular service.
![](https://i.imgur.com/ynFGEdp.png){: .full}

This is dry run result of angular service creation
![](https://i.imgur.com/oyCwe1b.png){: .full}

Fill out the form add below information
![](https://i.imgur.com/SZDx1N5.png){: .full}

Name: logging
project: branding-logger
Notice Logger service created
![](https://i.imgur.com/7aLT4Yn.png){: .full}

Lets run the test and see if the test is passing or not. Since I am using main branch instead of master branch I will update my scripts to take base as main branch only.

![](https://i.imgur.com/LQmjidP.png){: .full}

Since only logging service is added if I run the test only one project test will run.
Run npm run affected:test
![](https://i.imgur.com/owTmYZl.png){: .full}

## Step : Let's take logger dependency on our application

Next lest run the build
![](https://i.imgur.com/2OAeDSS.png){: .full}

npm run affected:build
![](https://i.imgur.com/wfr90IZ.png){: .full}

Notice the app is building and the dist folder is created with one app.

![](https://i.imgur.com/noosk8r.png){: .full}

Now let's use a logging service to log something and run our application next.

Go to libs/branding/logger/src/index.ts and export the logger service.

![](https://i.imgur.com/7w7SM23.png){: .full}

Next go to apps\cutepuppies-admin\src\app\app.component.ts and add logging service and log in constructor.
![](https://i.imgur.com/QGpa6da.png){: .full}

Lets serve our application run below script

nx serve cutepuppies-admin

![](https://i.imgur.com/wyde0hs.png){: .full}

Navigate to http://localhost:4200 and see in console log hello world is coming.

![](https://i.imgur.com/FMj0LWO.png){: .full}

Now lets build the application again and go to the dist folder and run below script from dist folder

cd dist/apps/cutepuppies-admin && npx http-server -o

Notice our app is running and I see the log as well.

![](https://i.imgur.com/GveyEna.png){: .full}

Creating Cute Puppies Client
![](https://i.imgur.com/KiVPRi2.png){: .full}

Created Sales/PuppyEditor
![](https://i.imgur.com/LrT06gn.png){: .full}

Creating sales/puppies

![](https://i.imgur.com/oRMOvDt.png){: .full}

![](https://i.imgur.com/M4nNi9M.png){: .full}

## Adding Users Library under Customers Service

![](https://i.imgur.com/fs31irh.png){: .full}

![](https://i.imgur.com/KbjCP4n.png){: .full}

![](https://i.imgur.com/69WJwUz.png){: .full}

![](https://i.imgur.com/fJda329.png){: .full}

![](https://i.imgur.com/0EXHyZr.png){: .full}

![](https://i.imgur.com/xsETtU5.png){: .full}

![](https://i.imgur.com/fZv6tcS.png){: .full}

Adding sales puppies route to client app.
![](https://i.imgur.com/B5PJ3BX.png){: .full}

Adding puppy editor route in admin app

![](https://i.imgur.com/XPNXHTP.png){: .full}

## Creating Add-Puppy Component on Puppy Editor project

![](https://i.imgur.com/KQcjsJL.png){: .full}

Declaring Module: libs/sales/puppy-editor/src/lib/sales-puppy-editor.module.ts

![](https://i.imgur.com/4Kn3o3C.png){: .full}

![](https://i.imgur.com/SJO5aT3.png){: .full}

![](https://i.imgur.com/Dc4DbjL.png){: .full}

![](https://i.imgur.com/u6Mj2Jx.png){: .full}

Check Dry Run result and confirm
![](https://i.imgur.com/09Ly6gw.png){: .full}

and select Run
![](https://i.imgur.com/BVo8q7V.png){: .full}

Component Created

![](https://i.imgur.com/3fGPE1t.png){: .full}

Component is good
![](https://i.imgur.com/Aze7pmz.png){: .full}

![](https://i.imgur.com/hzcmhnM.png){: .full}

## Add Puppies component in the Customers/Puppies using Nx Console.

![](https://i.imgur.com/I6UJayT.png){: .full}

![](https://i.imgur.com/ozBq2Tg.png){: .full}

To get the path of the component copy the relative path of lib folder of sales/puppies `/libs/sales/puppies/src/lib`

![](https://i.imgur.com/6Wh60db.png){: .full}

![](https://i.imgur.com/ybNcmwX.png){: .full}

![](https://i.imgur.com/1RdC1PS.png){: .full}

![](https://i.imgur.com/VuJK34K.png){: .full}

Select Run to create component

![](https://i.imgur.com/T57LNcC.png){: .full}

![](https://i.imgur.com/mFVIQJI.png){: .full}
![](https://i.imgur.com/nMdYTc8.png){: .full}
Lets update the routing for puppies
![](https://i.imgur.com/zfWzwRy.png){: .full}
Add route for add puppy in puppy editor
![](https://i.imgur.com/s6dEpx8.png){: .full}

### Adding routes for Admin App

Add route in admin app: add below route to navigate to puppy editor default component
![](https://i.imgur.com/CEJQgz9.png){: .full}

### Adding routes for Client App

Add route in client app: add below route to navigate to puppies module's default component.
![](https://i.imgur.com/eLa5JoV.png){: .full}

### Serving Admin component

Lets add scripts to serve both admin and client app

```json=
"start-admin":"nx serve cutepuppies-admin --port=4210 -o",
"start-client":"nx serve cutepuppies-client --port=4211 -o",
```

![](https://i.imgur.com/nEnnhWf.png){: .full}

Lets clean app component HTML

![](https://i.imgur.com/wmIXSdj.png){: .full}

Lets run the admin app `npm run start-admin`

![](https://i.imgur.com/Kn9feLH.png){: .full}

Admin Site is up and running
http://localhost:4210/puppies-editor

![](https://i.imgur.com/VE8KYyh.png){: .full}

## Serving client app

app component
![](https://i.imgur.com/cAGJAjc.png){: .full}

Run `npm run start-client`
![](https://i.imgur.com/SW5kU3k.png){: .full}

Client site is running : http://localhost:4211/puppies
![](https://i.imgur.com/o0iSvPJ.png){: .full}

## MonoRepo Workspace Architecture

**Apps**

- Apps are IT-Ops systems
- It can depend on anything
- Only apps are buildable and publishable to npm repositories.

**Libs**

- Libs are services
- Services should have multiple projects
- Services should not depend on each other
- Services projects should not depend on each other. Unless it is configured to do so.
- Services projects can depend on Branding
- Services projects are not buildable and not publishable
- Services projects has a libs folder which is equivalent to modules folder.

## MonoRepo Workspace Dependency Graph

Run `nx dep-graph --base=main`

![](https://i.imgur.com/1bA7G5Z.png){: .full}

## Creating Build CI pipeline

Install [yaml visual studio extension](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml)
![](https://i.imgur.com/T9rDvmQ.png){: .full}

Install [Azure Pipelines](https://marketplace.visualstudio.com/items?itemName=ms-azure-devops.azure-pipelines) for validations of yml file

![](https://i.imgur.com/D9VxmG9.png){: .full}

### Caching Azure Pipeline

We will install node modules and cache it so that for future build it will read from the cache location. If package-lock.json is changed it will refresh the cache.

We are going to use **Restores and saves pipeline artifacts with Universal Packages** to cache the ci pipelines. So Install the Task in your azure devops from marketplace.

[Restores and saves pipeline artifacts with Universal Packages](https://marketplace.visualstudio.com/items?itemName=1ESLighthouseEng.PipelineArtifactCaching)
![](https://i.imgur.com/pNN6xl4.png){: .full}

Since we are use pipeline cache, we need to create Artifacts Feed in Azure devops to store the node_modules folders. [Learn more about Artifacts Feed](https://docs.microsoft.com/en-us/azure/devops/artifacts/concepts/feeds?view=azure-devops)

## Create Artifact Feed in Azure devops

> Artifacts Feeds are organizational constructs that allow you to store, manage, and group your packages and control who to share it with. Feeds are not package-type dependent. You can store all the following package types in a single feed: npm, NuGet, Maven, Python, and Universal packages.

1. Go to Azure Artifacts.
   ![](https://i.imgur.com/DaCSK2x.png){: .full}
2. Select Create Feed.
   ![](https://i.imgur.com/jST8Fj8.png){: .full}
3. Give your feed a Name and choose its visibility, upstream sources and scope.
   ![](https://i.imgur.com/063qIt2.png){: .full}
   ![](https://i.imgur.com/r4XYaCa.png){: .full}

## Creating Azure CI Pipeline

Follow steps to create build definition

### Step 1: Create Template yaml File

Then go to project and create install-node-module.yml file:
![](https://i.imgur.com/fLed9Hi.png){: .full}

1. We will install node.js
2. We will write the task to cache the node_modules folder into the azure feed.
3. Then we will install node packages if cache does not exist.

```yaml
steps:
  - task: NodeTool@0
    inputs:
      versionSpec: '14.x'
    displayName: 'Install Node.js'
  - task: 1ESLighthouseEng.PipelineArtifactCaching.RestoreAndSaveCacheV1.RestoreAndSaveCache@1
    inputs:
      keyfile: '**/package-lock.json, !**/node_modules/**/package-lock.json, !**/.*/**/package-lock.json'
      targetfolder: '$(Build.SourcesDirectory)/node_modules'
      vstsFeed: 'nx_azure_node_modules_cache_feed'
  - script: |
      npm ci --ignore-engines
    displayName: Install dependencies only if there is no cache available
    condition: ne(variables['CacheRestored'], 'true')
```

### Step 2: Generate the ci script dynamically

![](https://i.imgur.com/yRtHDzM.png){: .full}

```javascript
/**
 * # Generate Ci command
 * 1. It will identify the affected projects
 * 2. Group the projects in 3 groups for each command.
 * ## Example:
 *  If 3 projects are affected it will create below group for lint, test and build command
 *          lint1:[admin], lint2:[logger], lint3:[client]
 *          build1:[admin], build2:[logger], build3:[client]( if you made buildable for each projects)
 *          test1:[admin], test2:[logger], test3:[client]( if you have tests for each projects)
 *  If 4 projects are affected it will create below group for lint, test and build command
 *          lint1:[admin,ngmaterial], lint2:[logger], lint3:[client]
 *          build1:[admin,ngmaterial], build2:[logger], build3:[client]( if you made buildable for each projects)
 *          test1:[admin,ngmaterial], test2:[logger], test3:[client] ( if you have tests for each projects)
 */

const execSync = require('child_process').execSync;
const isMaster = process.argv[2] === 'False';
const baseSha = isMaster ? 'origin/main~1' : 'origin/main';

console.log(
  JSON.stringify({
    ...commands('lint'),
    ...commands('test'),
    ...commands('build'),
  })
);

function commands(target) {
  const array = JSON.parse(
    execSync(`npx nx print-affected --base=${baseSha} --target=${target}`)
      .toString()
      .trim()
  ).tasks.map((t) => t.target.project);

  array.sort(() => 0.5 - Math.random());
  const third = Math.floor(array.length / 3);
  const a1 = array.slice(0, third);
  const a2 = array.slice(third, third * 2);
  const a3 = array.slice(third * 2);
  return {
    [target + '1']: a1,
    [target + '2']: a2,
    [target + '3']: a3,
  };
}
```

### Step : Create azure-pipelines.yml file

![](https://i.imgur.com/2oCIB4J.png){: .full}

```yaml
trigger:
  - main # Trigger CI automatically whenever main branch is changed

jobs:
  - job: initial_setup # Install Node.js & Node Packages & Generate Commands for Affected Projects.
    pool:
      vmImage: 'ubuntu-latest'
    variables:
      IS_PR: $[ eq(variables['Build.Reason'], 'PullRequest') ] # Findout Is this pull request?
    steps:
      - template: .azure-pipelines/steps/install-node-modules.yml # Base Template
      - powershell: echo "##vso[task.setvariable variable=COMMANDS;isOutput=true]$(node ./tools/scripts/generate-ci-commands.js $(IS_PR))" # Create COMMANDS build time variable and assign ci commands.
        name: setCommands
      - script: echo $(setCommands.COMMANDS) # Echo the command for log purpose.
        name: echoCommands
```

### Step : Lets Run the Build

![](https://i.imgur.com/GOUP7Se.png){: .full}

Select run
![](https://i.imgur.com/sO8rVJ0.png){: .full}

This time we have not changed the code therefore no build command created.
![](https://i.imgur.com/JxNUOsa.png){: .full}

### Step : Create Run Many JavaScript

![](https://i.imgur.com/bEu4amr.png){: .full}

In order to run the lint, test and build we have to create run-many.js file where we will put our script.

```javascript
/**
 * # Run Many
 * It will run the script using nx command line to run them in parellel.
 */

const execSync = require('child_process').execSync;

const commands = JSON.parse(process.argv[2]);
const projects = commands[process.argv[3]];
const target = process.argv[4];
execSync(
  `npx nx run-many --target=${target} --projects=${projects.join(
    ','
  )} --parallel`,
  {
    stdio: [0, 1, 2],
  }
);
```

### Step : Add lint, test and build scripts

```yaml
trigger:
  - main # Trigger CI automatically whenever main branch is changed

jobs:
  - job: initial_setup # Install Node.js & Node Packages & Generate Commands for Affected Projects.
    pool:
      vmImage: 'ubuntu-latest'
    variables:
      IS_PR: $[ eq(variables['Build.Reason'], 'PullRequest') ] # Findout Is this pull request?
    steps:
    CAMTASIA_19_MEDIA_FORMAT*C:\Users\Rupesh\Documents\Camtasia\Rec 01-21-21_003.trec|Product  - template: .azure-pipelines/steps/install-node-modules.yml # Base Template
      - powershell: echo "##vso[task.setvariable variable=COMMANDS;isOutput=true]$(node ./tools/scripts/generate-ci-commands.js $(IS_PR))" # Create COMMANDS build time variable and assign ci commands.
        name: setCommands
      - script: echo $(setCommands.COMMANDS) # Echo the command for log purpose.
        name: echoCommands

  - job: lint1 # Lets Run the Linting command for lint1 array.
    dependsOn: initial_setup
    condition:
      | # Make sure this is passing and Don't Run this if we have empty array in nx commands from intial_setup step.
      and(
        succeeded(),
        not(contains(
          dependencies.initial_setup.outputs['setCommands.COMMANDS'],
          '"lint1":[]'
        ))
      )
    pool:
      vmImage: 'ubuntu-latest'
    variables:
      COMMANDS: $[ dependencies.initial_setup.outputs['setCommands.COMMANDS'] ]
    steps:
      - template: .azure-pipelines/steps/install-node-modules.yml
      - script: node ./tools/scripts/run-many.js '$(COMMANDS)' lint1 lint # Run the lint command in parallel

  - job: lint2
    dependsOn: initial_setup
    condition: |
      and(
        succeeded(),
        not(contains(
          dependencies.initial_setup.outputs['setCommands.COMMANDS'],
          '"lint2":[]'
        ))
      )
    pool:
      vmImage: 'ubuntu-latest'
    variables:
      COMMANDS: $[ dependencies.initial_setup.outputs['setCommands.COMMANDS'] ]
    steps:
      - template: .azure-pipelines/steps/install-node-modules.yml
      - script: node ./tools/scripts/run-many.js '$(COMMANDS)' lint2 lint

  - job: lint3
    dependsOn: initial_setup
    condition: |
      and(
        succeeded(),
        not(contains(
          dependencies.initial_setup.outputs['setCommands.COMMANDS'],
          '"lint2":[]'
        ))
      )
    pool:
      vmImage: 'ubuntu-latest'
    variables:
      COMMANDS: $[ dependencies.initial_setup.outputs['setCommands.COMMANDS'] ]
    steps:
      - template: .azure-pipelines/steps/install-node-modules.yml
      - script: node ./tools/scripts/run-many.js '$(COMMANDS)' lint3 lint

  - job: test1
    dependsOn: initial_setup
    condition: |
        and(
          succeeded(),
          not(contains(
            dependencies.initial_setup.outputs['setCommands.COMMANDS'],
            '"test1":[]'
          ))
        )
    pool:
      vmImage: 'ubuntu-latest'
    variables:
      COMMANDS: $[ dependencies.initial_setup.outputs['setCommands.COMMANDS'] ]
    steps:
      - template: .azure-pipelines/steps/install-node-modules.yml
      - script: node ./tools/scripts/run-many.js '$(COMMANDS)' test1 test

  - job: test2
    dependsOn: initial_setup
    condition: |
      and(
        succeeded(),
        not(contains(
          dependencies.initial_setup.outputs['setCommands.COMMANDS'],
          '"test2":[]'
        ))
      )
    pool:
      vmImage: 'ubuntu-latest'
    variables:
      COMMANDS: $[ dependencies.initial_setup.outputs['setCommands.COMMANDS'] ]
    steps:
      - template: .azure-pipelines/steps/install-node-modules.yml
      - script: node ./tools/scripts/run-many.js '$(COMMANDS)' test2 test

  - job: test3
    dependsOn: initial_setup
    condition: |
      and(
        succeeded(),
        not(contains(
          dependencies.initial_setup.outputs['setCommands.COMMANDS'],
          '"test3":[]'
        ))
      )
    pool:
      vmImage: 'ubuntu-latest'
    variables:
      COMMANDS: $[ dependencies.initial_setup.outputs['setCommands.COMMANDS'] ]
    steps:
      - template: .azure-pipelines/steps/install-node-modules.yml
      - script: node ./tools/scripts/run-many.js '$(COMMANDS)' test3 test

  - job: build1
    dependsOn: initial_setup
    condition: |
      and(
        succeeded(),
        not(contains(
          dependencies.initial_setup.outputs['setCommands.COMMANDS'],
          '"build1":[]'
        ))
      )
    pool:
      vmImage: 'ubuntu-latest'
    variables:
      COMMANDS: $[ dependencies.initial_setup.outputs['setCommands.COMMANDS'] ]
    steps:
      - template: .azure-pipelines/steps/install-node-modules.yml
      - script: node ./tools/scripts/run-many.js '$(COMMANDS)' build1 build`

  - job: build2
    dependsOn: initial_setup
    condition: |
      and(
        succeeded(),
        not(contains(
          dependencies.initial_setup.outputs['setCommands.COMMANDS'],
          '"build2":[]'
        ))
      )
    pool:
      vmImage: 'ubuntu-latest'
    variables:
      COMMANDS: $[ dependencies.initial_setup.outputs['setCommands.COMMANDS'] ]
    steps:
      - template: .azure-pipelines/steps/install-node-modules.yml
      - script: node ./tools/scripts/run-many.js '$(COMMANDS)' build2 build

  - job: build3
    dependsOn: initial_setup
    condition: |
      and(
        succeeded(),
        not(contains(
          dependencies.initial_setup.outputs['setCommands.COMMANDS'],
          '"build3":[]'
        ))
      )
    pool:
      vmImage: 'ubuntu-latest'
    variables:
      COMMANDS: $[ dependencies.initial_setup.outputs['setCommands.COMMANDS'] ]
    steps:
      - template: .azure-pipelines/steps/install-node-modules.yml
      - script: node ./tools/scripts/run-many.js '$(COMMANDS)' build3 build

```

### Step : Lets Run the build Again

Notice since we have not changed any code we will notice only initial_setup and rest all jobs will be skipped.

![](https://i.imgur.com/QiHKC9V.png){: .full}

### Step : Lets Change the Logger and find out affected dependency graph

Go libs\branding\logger\src\lib\logging.service.ts
![](https://i.imgur.com/aeU11m5.png){: .full}

Run `npm run affected:dep-graph`

![](https://i.imgur.com/Tu2E3ML.png){: .full}

confirm changes are working Run `npm run start-admin`

![](https://i.imgur.com/iVTsegC.png){: .full}

### Step: Fix admin specs

Lets create a script to test and watch
![](https://i.imgur.com/FTvQoP8.png){: .full}

Now lets fix the test for admin project correct the title name
Now run `npm run affected:test`

It will automatically run the admin test.

![](https://i.imgur.com/zxF2qE5.png){: .full}

### Step: Fix client specs

Now lest fix the test for client project correct the title name
Now run `npm run affected:test`
It will automatically run the both admin & client test.
![](https://i.imgur.com/WAnxb3L.png){: .full}

![](https://i.imgur.com/8tn43Vi.png){: .full}

### Step : Lets Push the code and notice our Builds

See this time in the build machine as well it identified

1. Only 2 projects to lint and test and they are
   1. "branding-logger","cutepuppies-admin"
2. Only 1 Project to build and that is:"cutepuppies-admin"

Notice test and build are passing

![](https://i.imgur.com/Yj8uQdv.png){: .full}

### Step : Running all lint build and test as TASK

We dont want to trigger these many jobs since our monorepo is not that large. Therefore, I am deciding to create just one job so lets follow below steps.

### Step: Update the command generation script

Lets update the build definition to run them as task within single job.

Rename the current file to generate-ci-batch-commands.js
And create new file generate-ci-commands.js
![](https://i.imgur.com/RK1V28L.png){: .full}

```javascript
/**
 * # Generate Ci command
 * 1. It will identify the affected projects
 * 2. Group the projects in 3 groups for each command.
 * ## Example:
 *  If 3 projects are affected it will create below group for lint, test and build command
 *          lint1:[admin], lint2:[logger], lint3:[client]
 *          build1:[admin], build2:[logger], build3:[client]( if you made buildable for each projects)
 *          test1:[admin], test2:[logger], test3:[client]( if you have tests for each projects)
 *  If 4 projects are affected it will create below group for lint, test and build command
 *          lint1:[admin,ngmaterial], lint2:[logger], lint3:[client]
 *          build1:[admin,ngmaterial], build2:[logger], build3:[client]( if you made buildable for each projects)
 *          test1:[admin,ngmaterial], test2:[logger], test3:[client] ( if you have tests for each projects)
 */
debugger;
const execSync = require('child_process').execSync;
const isMaster = process.argv[2] === 'False';
const baseSha = isMaster ? 'origin/main~1' : 'origin/main';

console.log(
  JSON.stringify({
    ...commands('lint'),
    ...commands('test'),
    ...commands('build'),
  })
);

function commands(target) {
  const array = JSON.parse(
    execSync(`npx nx print-affected --base=${baseSha} --target=${target}`)
      .toString()
      .trim()
  ).tasks.map((t) => t.target.project);

  return { [target]: array };
}
```

If you run this script, after changing logger project. It will generate the commands for the affected projects. Like below

```json=
{"lint":["cutepuppies-admin","branding-logger"],"test":["cutepuppies-admin","branding-logger"],"build":["cutepuppies-admin"]}
```

![](https://i.imgur.com/IiVl5jO.png){: .full}

### Step : Update the azure-pipeline yml to have Steps not jobs

Rename the current azure-pipeline yml
![](https://i.imgur.com/tNAGfrK.png){: .full}

and move to .azure-pipeline/steps folder for future use or backup.

![](https://i.imgur.com/67QekSa.png){: .full}

azure-pipelines.yml

```yaml
trigger:
  - main # Trigger CI automatically whenever main branch is changed

variables:
  IS_PULLREQUEST: $[eq(variables['Build.Reason'], 'PullRequest')]

steps:
  - task: Cache@2
    displayName: 'Cache Npm Dependencies'
    inputs:
      key: '**/package-lock.json, !**/node_modules/**/package-lock.json, !**/.*/**/package-lock.json'
      path: '$(Build.SourcesDirectory)/node_modules'
      cacheHitVar: 'CacheRestored'

  - task: Npm@1
    displayName: 'npm ci'
    inputs:
      command: ci
      verbose: false
    condition: ne(variables['CacheRestored'], 'true')

  - powershell: |
      echo "##vso[task.setvariable variable=COMMANDS]$(node ./tools/scripts/generate-ci-commands.js $(IS_PULLREQUEST))"
    name: setCommands
    displayName: setting commands

  - script: echo $(COMMANDS)
    name: echoCommands
    displayName: commands to run

  - script: node ./tools/scripts/run-many.js '$(COMMANDS)' lint
    displayName: linting
    condition: |
      and(
        succeeded(),
        not(contains(
            variables['COMMANDS'],
            '"lint":[]'
        ))
      )

  - script: node ./tools/scripts/run-many.js '$(COMMANDS)' test
    displayName: testing
    condition: |
      and(
        succeeded(),
        not(contains(
            variables['COMMANDS'],
            '"test":[]'
        ))
      )
  - script: node ./tools/scripts/run-many.js '$(COMMANDS)' build
    displayName: building
    condition: |
      and(
        succeeded(),
        not(contains(
            variables['COMMANDS'],
            '"build":[]'
        ))
      )
```

Run build

![](https://i.imgur.com/Pjkjjwu.png){: .full}

### Step : Change logging service only and run build

![](https://i.imgur.com/tWw04V4.png){: .full}

Run build

![](https://i.imgur.com/IGmdmo1.png){: .full}

Build Success
![](https://i.imgur.com/8F5gXDb.png){: .full}

### Step : Finding affected apps

Lets update the commands to also give a list of apps to publish in npm repository.

When We change logger we want to also see publish array with affected app.

```json=
{"lint":["branding-logger","cutepuppies-admin"],"test":["branding-logger","cutepuppies-admin"],"build":["cutepuppies-admin"],"publish":["cutepuppies-admin"]}
```

If I change the client app as well then I should see both apps in publish array.

```json=
{"lint":["cutepuppies-client","branding-logger","cutepuppies-admin"],"test":["cutepuppies-client","branding-logger","cutepuppies-admin"],"build":["cutepuppies-client","cutepuppies-admin"],"publish":["cutepuppies-client","cutepuppies-admin"]}
```

I will add below method for getting publish apps

```javascript
function affectedApps(command) {
  const x = execSync(`npx nx affected:apps --base=${baseSha}`)
    .toString()
    .trim();

  let apps = x ? x.split('\n\n')[1].split(' - ').slice(1) : [];
  apps = apps.map((t) => t.replace('\n', '').trim());

  return { [command]: apps };
}
```

The new script for `generate-ci-command.js`

```javascript
const execSync = require('child_process').execSync;
const isMaster = process.argv[2] === 'False';
const baseSha = isMaster ? 'origin/main~1' : 'origin/main';

console.log(
  JSON.stringify({
    ...commands('lint'),
    ...commands('test'),
    ...commands('build'),
    ...affectedApps('publish'), // publish command for the apps
  })
);

function commands(target) {
  const array = JSON.parse(
    execSync(`npx nx print-affected --base=${baseSha} --target=${target}`)
      .toString()
      .trim()
  ).tasks.map((t) => t.target.project);

  return { [target]: array };
}

function affectedApps(command) {
  const x = execSync(`npx nx affected:apps --base=${baseSha}`)
    .toString()
    .trim();

  let apps = x ? x.split('\n\n')[1].split(' - ').slice(1) : [];
  apps = apps.map((t) => t.replace('\n', '').trim());

  return { [command]: apps };
}
```

### Step : Lets Add Package.json in applications

Admin app package.json
![](https://i.imgur.com/FBImW9k.png){: .full}

Client app package.json

![](https://i.imgur.com/dsaUa6N.png){: .full}

![](https://i.imgur.com/FtHLQEb.png){: .full}

### Step : Update workspace.json for app

In order to copy package.json file after build in the dist folder update the workspace file.

admin project
![](https://i.imgur.com/Wksie6X.png){: .full}

client project

![](https://i.imgur.com/FiXMBLL.png){: .full}

### Step : Build in Production Mode

I want to build my angular app with below

1. production mode
2. no output file hashing
3. I want source map file so that I can debug my source file.

Below is the nx build command to fulfill above requirements

```shell=
nx run-many --target=build --projects=cutepuppies-client,cutepuppies-admin --parallel --configuration=production --outputHashing=none --sourceMap=true
```

Run above nx build command

![](https://i.imgur.com/qFdZhxH.png){: .full}

Notice in the dist folder in admin folder we got map file and package.json
![](https://i.imgur.com/xZq2B3J.png){: .full}
client project
![](https://i.imgur.com/0v10ELf.png){: .full}

### Step: Publishing Test Results in Azure Pipeline Build

https://hackmd.io/ChTI9iFXQXGdlQAWrcqrKA

### Step: Publishing Code Coverage in Azure Pipeline Build

https://hackmd.io/Aiksk5NqQouDgKcZLjnHfQ

### Step: Add .npmrc file to app that we want to publish npm

Get access token from (npm.js)[https://www.npmjs.com/]

![](https://i.imgur.com/XIRXjjC.png){: .full}

![](https://i.imgur.com/ZXEZZYf.png){: .full}

Generating new access token in npmjs

![](https://i.imgur.com/VlwX0n3.png){: .full}

Adding npmrc file with authtoken
![](https://i.imgur.com/cHRfq8B.png){: .full}

![](https://i.imgur.com/aKO5rIy.png){: .full}

### Step: Updating Package.json Version & Publish Npm package

```javascript
/**
 * . bump the version
 * . add npmrc file (if required)
 * . publish to npm package repository
 *
 * Example: node ./publish-npm.js $(COMMANDS) $(Build.BuildNumber)
 *
 */

const execSync = require('child_process').execSync;
const fs = require('fs');
const path = require('path');
var basePackageJson = require('../../package.json');
const args = {
  commands: process.argv[2],
  buildNumber: process.argv[3],
};

console.log('Received Args: ', args, '\n');

if (!args.commands) {
  throw new Error('Commands are required');
}

const commands = JSON.parse(args.commands);
/*
let commands = {
  publish: ['cutepuppies-admin', 'cutepuppies-client'],
};
*/

if (!args.buildNumber) {
  throw new Error('Build Number is required');
}
const buildNumber = args.buildNumber.toString();
// let buildNumber = '3243';

const projects = commands['publish'];

const newVersion = getNewVesrion();

console.log(`new npm version would be: ${newVersion}`, '\n');

updatePublishingPackageJsonVersion();
publishNpmPackage();

return newVersion;

function getNewVesrion() {
  let currentVersion = basePackageJson.version;

  return currentVersion
    .split('.')
    .map((x, i) => (i == 2 ? buildNumber : x))
    .join('.');
}

function updatePublishingPackageJsonVersion() {
  projects.forEach((project) => {
    updateVersion(
      path.resolve(__dirname, '../../', `dist/apps/${project}/package.json`)
    );
  });
}

function updateVersion(packageJsonFilePath) {
  var package = require(packageJsonFilePath);
  package.version = newVersion;
  fs.writeFileSync(packageJsonFilePath, JSON.stringify(package, null, 2));

  console.log(
    `Version updated for the app ${package.name}: ${newVersion}`,
    '\n'
  );
}

function publishNpmPackage() {
  projects.forEach((app) => {
    const cwd = path.resolve(__dirname, '../../', `dist/apps/${app}`);
    console.log(`publishing to npm from: `, cwd, '\n');

    execSync(
      `npm publish --access public`,
      { cwd, stdio: [0, 1, 2] },
      function (error) {
        console.log(error, '\n');

        throw error;
      }
    );
    console.log(`${app} is published`, newVersion, '\n');
  });
}
```

### Step : Update Azure Pipelines to add publish Task

### Step : Push you changes and Trigger Build

See both admin and client is published.
![](https://i.imgur.com/yd4fgCr.png){: .full}

### Step: Only change Admin and Notice only Admin is published in NPM

![](https://i.imgur.com/vxX7r3e.png){: .full}

![](https://i.imgur.com/WKNOavp.png){: .full}

## Karma failing when no test present

Karma test will fail if u have not tests.
Therefore, if you want to stop this behavior then you need to go to `karma.conf.js` at root location where u see `package.json` and add below flag as false.

```json
    failOnEmptyTestSuite: false
```

## References
- Source Code : https://github.com/rupeshtiwari/coding-examples-angular-monorepo-with-nx
- https://github.com/rupeshtiwari/coding-examples-angular-monorepo-nx-azure-ci-cd 
- [An A-Z Index of the Windows CMD command line](https://ss64.com/nt/)

## Questions

- **Does the lib projects have npm versions?**
  **Answer:** No, because they are not buildable and publishable.

- **How should we branch in monorepo ?**
  **Answer:** V1, V2, V3 are the branches for the monorepo.

- **When do we create branches ?**
  **Answer:** As you move your code to a new environment it is recommended to create a separate branch in monorepo.

---

_Thanks for reading my article till end. I hope you learned something special today. If you enjoyed this article then please share to your friends and if you have suggestions or thoughts to share with me then please write in the comment box._

<div class="notice--success">
<strong>💖 Say 👋 to me!</strong>
<br>Rupesh Tiwari
<br>Founder of <a href="https://www.fullstackmaster.net">Fullstack Master </a>
<br>Email: <a href="mailto:rupesh.tiwari.info@gmail.com?subject=Hi">rupesh.tiwari.info@gmail.com</a>
<br>Website: <a href="https://www.rupeshtiwari.com">RupeshTiwari.com </a>
</div>
![](https://imgur.com/a32nUcu.png){: .full}
