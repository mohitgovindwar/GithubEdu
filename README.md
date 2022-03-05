# Hotel Website using Azure App Service.

## Steps to be followed:-

- I have created a new Azure Service on Microsoft Azure.
- Choosen Runtime stack as php 7.3 (Our application is just plain html+js+css though).
- Choosen region “Southeast Asia” (or try some other if it fails you need start all over again)
- And then changed the “size” to Basic B1.
- And then I clicked on "Review + Create" to create the Azure App Service.
- Now, I entered the domain I have recently purchased from namecheap.com
- Thus I have linked azure app service with a new custom domain.
- Then I created an remote repository on github.
- Then I have created a personal access token (In the scope I kept workflow as selected for allowing github actions/workflows).
- Added HTML,CSS and JavaScript content to repository using git bash.
- Then I Logged in into azure portal and then downloaded the “Publish Profile” for my App Service.
- Again I visited my Github repository in web browser and created a new “SECRET” to be used in “Github Action” 
-	Then went to my repository and then clicked on “Settings” for repository, then choose “Secrets”.
-	Now, creatde a new repository secret with name “PUBLISHPROFILE” and for value, copied the contents of “publishprofile” I have downloaded few steps back.
-	Now, I created a new empty Workflow for  my current repository by using “Actions” tab.
-	Once a workflow file (with default steps) is created, I just deleted the last two steps (highlighted).
-	Now, Added these lines (for azure app-service deployment)
  ```
      - name: Azure WebApp
        uses: Azure/webapps-deploy@v2
        with:
          app-name: githubwebsite
          publish-profile: ${{ secrets.PUBLISHPROFILE }}
   ```

- Then I commited the changes to workflow and checked the progress on next screen.
- For verification, please visit the web-site.
  [https://githubwebsite.azurewebsites.net/](https://githubwebsite.azurewebsites.net/)
  
- Thus I have deployed the website created using HTML, CSS and JavaScript using azure app service. 

