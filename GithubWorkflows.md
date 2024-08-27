# Github Workflow
A github workflow is a YAML configuration file in your repository's .github/workflows directory. 

## Events/triggers
Github Actions workflows are driven by events, which are activities that occur within your repository. 

### Code-related events: 
Push, Pull, Pull_request_review

### Issue and project management events 
issues, issue_comment, and milestone

### Schedule Events
Cron scheduled based for convenience similar to how DAGS are utilized

### Manual Events 
Triggering the event using
    workflow_dispatch: 

### Repository and Organization


### External Events 


### Github Actions with Environment Configurations 
If your repository has environments set up in it. You can utilize env specific environment variables from within your workflows. (Scoped Variables such as keys etc.)

Environment Variables take precedence over repository secrets

You can also lock down the deployments to selected approvers. Say a workflow is about to deploy to production, right before it does it will ask the approvers if it is okay to deploy or not.

Allows our team to be able to view what has been deployed to each environment and when. By doing so it allows for greater visibility of seeing what is currently in our deployed environments. <- This is the major benefit I see in utilizing it. 

Potential Advantages: 
1. Deployment Tracking:
- Visibility: knowing which branch is deployed
- Auditing: Track changes and deployments over time which help in compliance or regulatory requirements 

2. Environment Specific Configs 
- Secrets Management (Store env specific secrets)
- Configuration Management - Manage Configuration Files or settings tailored to each environment 

3. Workflow Orchestration 
- Complex Deployments: Github actions and environment can work together effectively
- Dependency Management: If your deployments have dependencies between environments, environments can help manage these relationships.

4. Automation 
Automated Deployments: Environments can be integrated with CI/CD pipelines for automated deployments, saving time and reducing errors. 

