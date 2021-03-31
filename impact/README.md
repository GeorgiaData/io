
# Industry Impact ML - Websocket Setup


Start localhost port 8777 with local io and localsite repos. [Getting started](../../localsite/start)  


Run in your <b>io/impact/src</b> folder to start the local websocket:

	python3 server.py
    
You will then see orange bars at the bottom. (If not, see the install.md file in this folder.)

The current websocket resides at:

ws://127.0.0.1:8181/

Therefore, [model.earth/io/impact](https://model.earth/io/impact/) also shows the orange bars if you have the websocket running locally.  

### How to run as a website

Next we need to add documentation on running as a website. Starting points:

[Adding Websockets to your AWS Serverless application](https://medium.com/artificial-industry/adding-websockets-to-your-aws-serverless-application-d8b1631754f6)  

[Websocket Tutorials — Python Serverless Microframework](https://aws.github.io/chalice/tutorials/websockets)

<!--
	Range slider
	https://github.com/niandco/range
-->

