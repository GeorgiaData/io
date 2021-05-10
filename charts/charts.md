# Embeddable IO Widgets
<div class="floatright">
<img src="../img/logo/epa.png" style="width:100%; max-width:200px; margin-left:30px">
</div>
[Local Industry Evaluator](../../localsite/info/) - Contains multiple widgets - Leaflet, JQuery and React  
[Getting started with localsite](https://model.earth/localsite/start/) - clone [io repo](https://github.com/modelearth/io/) and [localsite repo](https://github.com/localsite/localsite/) into the same web root.  

<!--
## Environmentally-Enabled <span style="white-space:nowrap">Input-Output Model</span>

In RStudio
Tools > Install Packages > devtools

OR

install.packages(‘devtools’)          
library(devtools)

Rstudio has devtools intalled already, so maybe just library(devtools) to call in the package
-->

<style>
</style>


## React Widgets

[View documentation and functions](https://msrocka.github.io/useeio-widget-builds/apidoc/) generated using [TypeDoc](https://typedoc.org/).  

The React widgets in the [io repo](https://github.com/modelearth/io/) originate from the EPA's [USEEIO-widgets repo](https://github.com/USEPA/useeio-widgets/).   
You can make widget updates in the [model.earth io repo](https://github.com/modelearth/io/) and we'll push into the EPA repo from [StateData](https://github.com/StateData/useeio-widgets/).  
The io repo includes additional code for displaying widgets. We also publish via the [io build folder](../build).  

- [Inflow-Outflow Chart](inflow-outflow/#sectors=333613,335912,336111&set=wealth&indicators=VADD) - (<a href="../build/slider.html#sectors=333613,335912,336111">Widget only</a>)<!-- &page=1&count=10 --><!-- [imfast.io](https://useeiowidgets.imfast.io/slider.html#sectors=322130,325520,327910,541200)-->  
- [Sector List - Mosaic](../build/sector_list.html?view=mosaic&count=50)  
- [Sector List - Mosaic Limit Sectors](../build/sector_list.html?naics=333613,335912,336111&view=mosaic&count=50)  
- [Sector List - Display Values](../build/sector_list.html?view=mosaic&showvalues=true)  
- [Sector List - One indicator](../build/sector_list.html#view=mosaic&indicators=WATR&showvalues=true)  
- [Sector List IO - Tire manufacturing (older version)](../build/iotables.html#sectors=326210&page=5)  
- [Industry Impact Bars with Configuration](../build/impact_chart_config.html)    
- [More React widgets](../build/) - ([Recent build](https://msrocka.github.io/useeio-widget-builds/))  

## JQuery Widgets 

- [Impact Bubble Chart](bubble/) - D3 and JQuery  
- [Sankey Chart](sankey/) - D3 with Python prep  


<!--
If your local widgets reference the "useeio" folder, they may need to be updated occasionally as parameters change. For stability, point your local widgets at one of the [numbered backups](https://model.earth/eeio/build.2020.002) or copy the useeio folder into your project.


([old version](https://model.earth/eeio/build.2020.001), [pre-React](https://model.earth/eeio/build.2020.003) and [new version](useeio)) 
-->

## Related Map Work

- [Simple embedded map sample](/localsite/info/embed.html)<!-- Remove: https://model.earth/community/impact/ -->  
- [PPE Supplier Map (from Google Sheet)](../../localsite/map/#show=suppliers) - Leaflet and JQuery  
- [Farm Fresh Produce Map (from CSV files on GitHub)](../../localsite/map/#show=farmfresh) - Leaflet and JQuery  

---
<br>


# Add or Edit Widgets

## Option 1: Embed Widgets

You may embed using a [pre-built static copy](../build). 

Using the static output, you can set parameters in the URL or javascript to control the display of the widgets.  

We've copied a static version of the widgets into the "modelearth/io" repo. 
You can use the Github links for embedding.

<!--
from the [GitHub source code](https://github.com/USEPA/useeio-widgets)
-->

## Option 2: Build and Edit Widgets Locally (React)

You can build the USEEIO React widgets locally.  
Start with one of the following repos:  


A. [https://github.com/modelearth/io](https://github.com/modelearth/io) - Contains a fork of [useeio-widgets](https://github.com/usepa/useeio-widgets), plus a built copy, JQuery widgets and extras (navigation and configuration examples).  

If you use the "io" repo, also clone the [https://github.com/localsite/localsite](https://github.com/localsite/localsite) repo and place it adjacent to the "io" repo.  Here's more info on [hosting the Localsite Framework on your computer](../../localsite/start/).

B. [USEEIO-widgets repo](https://github.com/USEPA/useeio-widgets/) - Only React widgets  


<!--After building the widgets, you will need an API key to download the industry sector data JSON files, or you can copy the JSON files from the pre-built static copy. Post an issue to request a key.  -->

---
### Steps for Building React Widgets
To build the React widgets locally you'll need a current version of
[Node.js](https://nodejs.org) installed. Make sure that the `node` and `npm`
commands are available in your systems path (you can test this via `node -v` and
`npm -v` on the command line which should give you the respective version of
these tools). 

Open a terminal or VS Code:     

A. You can right-click the repo folder and choose "New Terminal at Folder" on a Mac.  

B. Or you can open the folder from VS Code.  (Shortcut for opening VS Code: Open a command prompt in the repo folder and type `code .`  (This may be necessary if your build does not run when opening with File > Open.) You may need to [Configure your VS Code Editor](https://code.visualstudio.com/docs/setup/setup-overview) so running `code .` launches the editor.  Avoid running in the parent folder containing your repo(s) or your VS Code editor may not allow you to run subsequent commands inside its terminal.  

To open a command shell window within VS Code by typing (Ctrl + \` backtick) or go to the "View > Terminal". 

<!--

```
cd io
```

Or use <code>cd useeio-widgets</code> if you are just using the source repo.  
-->

#### Install Node.js Modules  

The following will add a node_modules folder containing javascript source libraries (dependencies) that will be used to output code for the widgets.  

```
npm install
```

<!--
You can ignore errors (about 11), including "Error: `gyp` failed with exit code: 1".  

If you receive a "high severity vulnerabilities" warning, run the following as advised:  

	npm audit fix
-->
<!--
pre-React and with React, ignored:
	`gyp` failed with exit code: 1
-->
Then build the widget libraries. (Note that if you are using the "io" repo you'll already have a pre-built "build" folder.)

```
npm run build
```

This will create or update the `build` folder and a `lib` sub-folder containing small JavaScript libraries used by the USEEIO widgets.  

Once built, the `build` folder contains [example HTML files](https://model.earth/io/build/) that demonstrate the usage of these widgets.  

### Generate Local JSON files from API

You can skip this step since we've already populated the **io/build/api folder** for you by generating static .json files from the staging API.

To provide data for the hosted widgets, we've download from the Staging instance of the
[USEEIO API](https://github.com/USEPA/USEEIO_API) via the following:

```
npm run download -- --endpoint https://smmtool.app.cloud.gov/api
```
Running the above mirrors data API into the static json files in the `build/api` folder. There are two subfolders for each model: national USEEIO and state GAUSEEIO for Georgia (and a third for upcoming v2 data).  

Sometimes we have to run the command above a second time to populate build/api/GAUSEEIO/demands table. (Aug 2020)  

Note: Every 90 days the staging server requires a reboot, email the [contact person](https://github.com/USEPA/USEEIO_API/wiki/People#Contact) to restart.  
If the '/api' address returns 404, you can use the staging 
<a href="https://smmtool.app.cloud.gov/" target="_blank">endpoint overview</a> to see if it is online.  

You may optionall [request the key](https://github.com/USEPA/USEEIO_API/wiki/Use-the-API) to the production API to run the following:  

```
npm run download -- --endpoint https://api.edap-cluster.com/useeio/api --apikey [Add API key here]
```
<div class="local" style="display:none;">
The production API requires an API key<!-- there is probably not a URL format-->
<a href="https://api.edap-cluster.com/?x-api-key=" target="_blank">endpoint overview</a>
</div>
Learn more about [using the USEEIO API](https://github.com/USEPA/USEEIO_API/wiki/Use-the-API)

Important: After generating build/api folder from the production API:  
<!--
1. Duplicate USEEIOv1.2 to USEEIO for existing script in non-React widgets.  
2. Duplicate USEEIOv1.2 to GAUSEEIO since GA data currently only resides on the staging server.  

Manually copy the GAUSEEIO to a new folder called USEEIOv1.2 for Inflow-Outflow Chart  
-->

Replace USEEIOv1.2 with USEEIOv2.0

You now have two options for viewing the widgets locally.

<b>Option 1:</b> Start a server using the command <code>npm run server</code>. 
Then open the default port (8080) at http://localhost:8080 in your browser to see the widgets.  Your command window will become inoperable since it is running a server.  Open a new command window (by clicking plus) to issue further commands.  

<b>Option 2:</b> View at the following URL if the "io" folder resides in your webroot. (Your port number may differ.) 

[http://localhost:8887/io/build](http://localhost:8887/io/build)  

If you are working in a direct fork of the "useeio-widgets" repo, view here:  

[http://localhost:8887/useeio-widgets/build](http://localhost:8887/useeio-widgets/build)  

Use the up-arrow to run the build line after making a change.  

	npm run build



View the output of your build at [http://localhost:8887/io/build](http://localhost:8887/io/build) 

Learn more in the VS Code [Node.js Tutorial](https://code.visualstudio.com/docs/nodejs/nodejs-tutorial). 

### You may also contribute to the USEEIO-widget repo directly

To make updates in the NodeJS source code, fork the [USEEIO-widgets](https://github.com/USEPA/useeio-widgets/) repo and save in your local webroot (where you've [pointed](../../localsite/start/) http://localhost:8887/)  

Edit the files that reside in useeio-widgets/src. (Avoid editing files in useeio-widgets/build, these will be overwritten when you run the build.) 

Build when editing - [Amplify React App](../../aws/amplify/) uses `npm start` to build on-the-fly.  
Another option: [LiveReload](https://www.logicbig.com/tutorials/misc/typescript/project-auto-refresh-with-live-reload.html) might refresh your browser as you edit.  
Install using the [Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery)  (Please update our documentation, not yet confirmed). 

Get under the hood! Mess with our [Python Samples](../../community/resources/useeio) and 
[add a new technology to the matrix using RStudio](../naics).

<!--
From the following:
https://stackoverflow.com/questions/18428374/commands-not-found-on-zsh

1. Use a good text editor like VS Code and open your .zshrc file (should be in your home directory. 

Command+Shift+H
Command+Shift+Dot

if you don't see it, be sure to right-click in the file folder when opening and choose option to 'show hidden files').

2. find where it states: export PATH=a-bunch-of-paths-separated-by-colons:

3. insert this at the end of the line, before the end-quote: :$HOME/.local/bin

-->

## FAQs

### Why are some values in the demand vector $0 (blank)?

In some cases there is no final demand for the respective commodity and the production of that commodity is only driven by intermediate industry transactions (note that there are different demand vectors in the model and that the selected demand can be controlled via the configuration attributes). 


### How is code formatting enforced?

The `.editorconfig` file contains the formatting settings. Modern editors have plugins for checking EditorConfig settings. This maintains consistency so we can see in the diffs what changed. There is also a ESLint configuration in the project for other settings like semicolon rules etc.


## Sustainable Communities Web Challenge

[Get involved with our 2021 Sustainable Communities Web Challenge](https://model.earth/community/challenge) - $10,000&nbsp;in&nbsp;awards!  
