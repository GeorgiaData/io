# Javascript with Python - <span style='white-space:nowrap'>Machine Learning Tools for PUMA</span> 

### Environmentally-Enabled Impact Evaluator

Focus: Tools combining [NAICS industry groups (284)](https://datausa.io/search/?dimension=PUMS%20Industry) with [Input-Output Visualizations](../../localsite/info/) for [Electric Vehicle Manufacturing Transitions](../../community/projects/mobility/) and [Bioeconomy Waste-to-Energy analysis](../../localsite/info/#show=bioeconomy).

- Top industry groups based on Public Use Microdata Areas (PUMAs)  
- Impact graphs for sets of locations and industries within [EV Transition Evaluator](../../localsite/info/#show=vehicles)  

### Implementation

1. Set up a GitHub action to pull industry group concentration from<br>[DataUSA.io API](https://datausa.io/about/api/) or [Google Data Commons API](https://docs.datacommons.org/api/)<br>[Store as CSV files by state on GitHub](https://www.google.com/search?q=github+actions+send+data+to+csv+file) in the [Community-Data repo](https://github.com/modelearth/community-data).  

2. Apply machine learning using public websocket.<br>Document deployment of existing websocket for [Industry Hotspot Python](https://model.earth/io/impact/).<br>  
Python server-side: [Flask to Google Cloud with Docker/Kubernetes](https://medium.com/honeybadger-ai/how-to-deploy-machine-learning-models-using-flask-docker-and-google-cloud-platform-gcp-6e7bf1b339d5)  
Websocket API: [Amazon API Gateway and AWS Lambda with DynamoDB](https://www.youtube.com/watch?v=DzpGfyB0iKk)  

3. Update and Integrate US EPA Environmentally-Enabled [Input Output widgets](../charts/).  

Lead Intern: John A Taylor  
Collaborators: Loren Heyns, Costas Simoglou  
Focus: West Central Georgia and Southeast Coastal Georgia   


