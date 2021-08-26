# Deploy Flask Machine Learning Application on Azure App Services

Here are the actions we'll be performing: 
1. Set up an Azure App Service flask app and deploy it 
2. Integrate it with Azure Pipelines 
3. Test Continuous Delivery (CD) 
4. Enhance CD with quality control gates via pylint. 

## Set Up Azure Pipelines

- Launch Cloud shell
- Set up the GitHub Repo and integrate Azure Pipelines from the GutHub Marketplace
- Clone this repository in the enviroment
- ```cd``` into the directory
```
cd flask-ml-AzureDevOps-serverlss
```
- Set up a virtual enviroment 
```
python3 -m venv ~/.flask-ml-AzureDevOps
source ~/.flask-ml-AzureDevOps/bin/activate
```
- Run the ```make install``` command to install the dependencies from the ```makefile```.
- Create an app service and deploy as well then verify 
```az webapp up -n <your-appservice>```; choose any name for your appservice. Verify by running the link in your browser 
```
https://<your-appservice>.azurewebsites.net/
```
- Perform prediction by changing the  ```make_predict_azure_app.sh``` file to match the app service URL
- Create an Azure DevOps Project using this [documentation](https://docs.microsoft.com/en-us/azure/devops/pipelines/ecosystems/python-webapp?view=azure-devops)
- Set up a Continuous Delivery Workflow following this [documentation](https://docs.microsoft.com/en-us/azure/devops/pipelines/ecosystems/python-webapp?view=azure-devops) as well. The good thing is the template has it all figured out for your application. 
- Check your build and confirm it's working, probably get a status badge and update your READme
