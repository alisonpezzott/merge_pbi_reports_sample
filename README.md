[![deploy](https://github.com/alisonpezzott/merge_pbi_reports_sample/actions/workflows/deploy.yml/badge.svg)](https://github.com/alisonpezzott/merge_pbi_reports_sample/actions/workflows/deploy.yml)  
 

# Power BI Projects Workflow

## What is this?  

This repository is a example how to work in collaboration with Power BI Projects using Git and GitHub Workflow resolving conflicts and building a parallel project sample. 
It demonstrates the use of a CI/CD scenario for Microsoft Power BI PRO projects by utilizing [fabric-cli](https://aka.ms/fabric-cli) and GitHub Actions.  


## Quick Links  
- Video demo of this repo: Soon    


## Instalation 

- Fork this repo  
- Rename the `.env.example`  to `.env`  and fill with the SPN secrets    
- Configure the same SPN secrets on GitHub Actions if you want CD


|Name|Value|  
|---|---|  
|FABRIC_CLIENT_ID|Your Service Principal Client ID from Entra App ID|  
|FABRIC_CLIENT_SECRET|Your Service Principal Secret from Entra App ID|  
|FABRIC_TENANT_ID|Your Tenant ID|  


If you run locally, in the first time install the requirements with:    

```bash
$ pip install -r requirements.txt  
```

- Configure  the file `config.json` with ids by branch.  
  - The  adminUPNs are the Object ID of the Entra User Principal Name.  


## CI/CD Pipeline  

- The Power BI Projects are saved in the `src` folder with the extensions `*.Report` and `*.SemanticModel`.  
- Deploying new versions is done on the `dev` branch.  
- On every Pull Request to `develop`, the GitHub Actions pipeline called `.github\workflows\bpa.yml` is triggered, running the best practices analysis pipeline. This process utilizes community tools such as [Tabular Editor](https://github.com/TabularEditor/) and [PBI-Inspector](https://github.com/NatVanG/PBI-InspectorV2). If approved and merged the pipeline `.github\workflows\deploy.yml`  will deploy to the workspace `*-DEV` workspace with the name and data source specified in `config.json`.  
 - Once the project is approved, a pull request is created for the `main` branch, where the pipeline will deploy the version to the workspace `*-PRD` workspace following the same `config.json`.  


## Contributing  

- If you would like to help fund or sponsor the project, you can do via [💗 GitHub Sponsors](https://github.com/sponsors/alisonpezzott) or yet via [YouTube](https://youtube.com/@alisonpezzott).  
- This is just one suggested approach in a world of countless possibilities and diverse structures.  
You can and should use this repository as inspiration and a technical foundation to build more sophisticated and robust pipelines if needed for your application. If you are a dev and discover issues or alternative ways, submit your pull requests to apreciation if you wish to contribute with code for the project.  
- Other ways to contribute are by helping people out with support on our forums or in our community. You can access them on the below links.  

[![YouTube subscribers](https://img.shields.io/youtube/channel/subscribers/UCst_4Wi9DkGAc28uEPlHHHw?style=flat&logo=youtube&logoColor=ff0000&colorA=2E3440&colorB=FFFFFF)](https://www.youtube.com/@alisonpezzott?sub_confirmation=1)
[![GitHub followers](https://img.shields.io/github/followers/alisonpezzott?style=flat&logo=github&logoColor=ffffff&colorA=2E3440&colorB=FFFFFF)](https://github.com/alisonpezzott)
[![LinkedIn](https://custom-icon-badges.demolab.com/badge/LinkedIn-0A66C2?logo=linkedin-white&logoColor=fff)](https://linkedin.com/in/alisonpezzott)
[![Discord](https://img.shields.io/badge/Discord-%235865F2.svg?&logo=discord&logoColor=white)](https://discord.gg/sJTDvWz9sM)
[![Telegram](https://img.shields.io/badge/Telegram-2CA5E0?logo=telegram&logoColor=white)](https://t.me/alisonpezzott)
[![Instagram](https://img.shields.io/badge/Instagram-%23E4405F.svg?logo=Instagram&logoColor=white)](https://instagram.com/alisonpezzott)  











