
<properties
	pageTitle="Team Data Science Process: An Overview"
	description="An outline of the key components of the Team Data Science Team."  
	services="machine-learning"
	documentationCenter=""
	authors="bradsev"
	manager="jhubbard"
	editor="cgronlun" />

<tags
	ms.service="machine-learning"
	ms.workload="data-services"
	ms.tgt_pltfrm="na"
	ms.devlang="na"
	ms.topic="article"
	ms.date="09/22/2016"
	ms.author="bradsev;hangzh;"/>

# Team Data Science Process: An Overview

The Team Data Science Process (TDSP) is an agile, iterative data science methodology to deliver predictive analytics solutions and intelligent applications efficiently. TDSP helps improve team collaboration and learning. TDSP is a distillation of the best practices and structures from Microsoft and others in the industry that facilitate the successful implementation of data science initiatives that help companies fully realize the benefits of their analytics program.

This article provides an overview of TDSP and its main components. We provide a generic description of the process here that can be implemented with a variety of tools. In the detailed articles, we also provide guidance on how to implement the TDSP using a specific set of Microsoft tools and infrastructure that we use to implement the TDSP in our teams. 

## Key components of the TDSP

TDSP comprises of the following key components :  

* A **data science lifecycle** definition.  
* A **standardized structure for projects** 
* **Analytics infrastructure** management 
* **Productivity Tools and utilities**  

## 1. Data Science Lifecycle 

Data Science is a highly iterative discovery process with emphasis on evaluating and validating each step of the process. The process iterations refine the hypotheses and predictive models to obtain a sound solution. The data science lifecycle defines a systematic sequence of steps that starts with the planning step, where the business problem is framed, proceeds to the development of predictive analytics models, and completes with their consumption of predictions by intelligent applications. If you are using an existing lifecycle like [CRISP-DM](https://wikipedia.org/wiki/Cross_Industry_Standard_Process_for_Data_Mining), [KDD](https://wikipedia.org/wiki/Data_mining#Process) or your own custom process that is working well in your organization, you can still use TDSP in the context of those development lifecycles. If you dont have one in use already, TDSP provides a staged data science lifecycle for you to adopt. At a high level, the different methodologies have much in common. You can easily map the correspondences between the steps in the TDSP lifecycle and in these other popular methodologies. Here is a depiction of the TDSP lifecycle. 

![TDSP_LIFECYCLE](./media/team-data-science-process-overview/tdsp-lifecycle.png) 

Details of each stage of the lifecycle in TDSP are found [here](team-data-science-process-lifecycle-detail.md). 

The following diagram provides the detailed task view for each of the role working together on a data science initiative in each stage of the lifecycle. The prescribed documentation artifacts are indicated in the diagram too. 

![TDSP_SWIMLANE](./media/team-data-science-process-overview/tdsp-swimlane.png)

## 2. Standardized structure for projects
Having all projects share a directory structure and use templates for project documents makes it easy for the team members to find information about their projects. All code and documents are stored in a version control system (VCS) like Git, TFS, or Subversion to enable team collaboration. Tracking tasks and features in an Agile project tracking system like Jira, Rally, Visual Studio Team Services, and optionally linking them to a VCS allows closer tracking of code for individual features and enables teams to obtain better cost estimates. TDSP recommends creating a separate **repository** for each project on the VCS for versioning, information security, and collaboration. The standardized structure for all projects helps build institutional knowledge across the organization. 

We provide templates for the folder structure and required documents. The folder structure organizes files such as code for data exploration, feature extraction, and model iterations in standard locations. This makes it easier for team members to understand work done by others and to add new members to teams. It is easy to view and update document templates in markdown format. Use templates to provide checklists with key questions for each project to insure deliverables meet the quality expected . Examples include:

* a project charter to document the business problem and scope of the project 
* data reports to document the structure and statistics of the raw data
* model reports to document the derived features
* model performance metrics such as ROC curves or MSE

![TDSP_DIR_STRUCT](./media/team-data-science-process-overview/tdsp-dir-structure.png) 

The directory structure can be cloned from [Github](https://github.com/Azure/Azure-TDSP-ProjectTemplate). 

## 3. Management of Analytics Infrastructure
TDSP provides recommendations for managing shared analytics and storage infrastructure such as cloud file systems for storing datasets, databases, Big Data (Hadoop, Spark) clusters, and machine learning services. The analytics and storage infrastructure can be on the cloud or On-premises. This is where raw and processed datasets are stored. This infrastructure enables reproducible analysis. It also avoids duplication, which can lead to inconsistencies and unnecessary infrastructure costs. Tools are provided to provision the shared resources, track them, and allow each team member to connect to those resources securely. It is also a good practice have project members create a consistent compute environment so experiments can be replicated and validated by different team members. 

Here is an example of a team working on multiple projects and sharing various cloud analytics infrastructure components. 

![TDSP_INFRA](./media/team-data-science-process-overview/tdsp-analytics-infra.png)
## 4. Productivity tools and utilities

Introducing processes in most organizations is challenging. By providing tools to implement the data science process and lifecycle, we not only get the benefits of productivity but also of consistency in its adoption. TDSP provides an initial set of tools and scripts to jump start adoption of TDSP within a team and to automate some of the common tasks in the data science lifecycle such as data exploration and baseline modeling. There is a well-defined structure provided for individuals to contribute shared tools and utilities into their team’s shared code repository.  These resources can then be leveraged by other projects within the team or the organization. In future TDSP also plans to enable the contributions of tools and utilities to the whole community. 
The TDSP utilities can be cloned from [Github](https://github.com/Azure/Azure-TDSP-Utilities). 

## Next steps: [Team Data Science Process: Roles and tasks](./team-data-science-process-roles-tasks.md)

<properties
	pageTitle="Team Data Science Process: components, roles and tasks"
	description="An outline of the key components, personel roles, and associated tasks for a data science team."  
	services="machine-learning"
	documentationCenter=""
	authors="bradsev"
	manager="jhubbard"
	editor="cgronlun" />

<tags
	ms.service="machine-learning"
	ms.workload="data-services"
	ms.tgt_pltfrm="na"
	ms.devlang="na"
	ms.topic="article"
	ms.date="09/20/2016"
	ms.author="bradsev;hangzh;"/>

# Team Data Science Process: Roles and tasks

The [Team Data Science Process](README.md) (TDSP) is a framework developed by Microsoft that provides a 
structured methodology to build predictive analytics solutions and intelligent applications efficiently. 
This article outlines the key personnel roles, and their associated tasks that are handled by a data science team standardizing on this process. 
This introduction links to tutorials that provide instructions on how to set up the TDSP environment for the entire data science group, data science teams, and projects. 
We provide detailed guidances using Visual Studio Team Services (VSTS) in the tutorials as our code-hosting platform and agile planning tool to manage team tasks, control access, and manage the repositories. 
You will be able to use this information to implement TDSP on your own code-hosting and agile planning tool. 

## Definition of four TDSP roles

We have specified four distinct roles for our team personnel:

1. ***Group Manager***. Group Manager is the manager of the entire data science unit in an enterprise. A data science unit might have multiple teams, each of which is working on multiple data science projects in distinct business verticals. A Group Manager might delegate their tasks to a surrogate, but the tasks associated with the role do not change.

2. ***Team Lead***. A team lead is managing a team in the data science unit of an enterprise. A team consists of multiple data scientists. For data science unit with only a small number of data scientists, the Group Manager and the Team Lead might be the same person.

3. ***Project Lead***. A project lead manages the daily activities of individual data scientists on a specific data science project. 

4. ***Project Individual Contributor (Data Scientist, Business Analyst, Data Engineer, Architect, etc)***. A project individual contributor executes a data science project. 

NOTE: Depending on the team, a single person may play more than one roles OR there may be more than one person working on a role. 

## Tasks to be completed by four personnel

The following picture depicts the top-level tasks for personnel by role in adopting and implementing the Team Data Science Process as conceptualized by Microsoft. 

![PROJECT_EXECUTE](./media/team-data-science-process-overview-components-roles-tasks/overview-tdsp-top-level.png)

This schema and the following, more detailed outline of tasks that are assigned to each role in the TDSP should help you choose the appropriate tutorial based on your responsibilities in the organization.

>[AZURE.NOTE] In the following instructions, we show steps of how to set up a TDSP environment and complete other data science tasks in Visual Studio Team Services (VSTS). We specify how to accomplish these tasks with VSTS because that is what we are using to implement TDSP at Microsoft. VSTS facilitates collaboration by integrating the management of work items that track tasks and a code hosting service used to share utilities, organize versions, and provide role-based security. You are able to choose other platforms, if you prefer, to implement the tasks outlined by the TDSP. But depending on your platform, some features we leverage from VSTS may not be available. 
We also use the [Data Science Virtual Machine (DSVM)](http://aka.ms/dsvm) on the Azure cloud as the analytics desktop with several popular data science tools pre-configured and integrated with various Microsoft software and Azure services. You can use the DSVM or any other development environment to implement TDSP. 


## Group Manager tasks

The following tasks are completed by the Group Manager (or a designated TDSP system administrator) to adopt the TDSP:

- Create a **group account** on a code hosting platform (like GitHub, Git, VSTS, or others)
- Create a **project template repository** on the group account, and seed it from the project template repository developed by Microsoft TDSP team. The TDSP project template repository from Microsoft provides a **standardized directory structure** including directories for data, code, and documents, and provides a set of **standardized document templates** to guide an efficient data science process. 
- Create a **utility repository**, and seed it from the utility repository developed by Microsoft TDSP team. The TDSP utility repository from Microsoft provides a set of useful utilities to make the work of a data scientist more efficient, including utilities for interactive data exploration, analysis, and reporting, and for baseline modeling and reporting.
- Set up the **security control policy** of these two repositories on your group account.  

For detailed step-by-step instructions, see [Group Manager tasks for a data science team](team-data-science-process-group-manager-tasks.md). 


## Team Lead tasks

The following tasks are completed by the Team Lead (or a designated team project administrator) to adopt the TDSP:

- If VSTS is selected to be the code hosting platform for versioning and collaboration, create a **team project** on the group's VSTS server. Otherwise, this task can be skipped.
- Create the **team project template repository** under the team project, and seed it from the group project template repository set up by your group manager or the delegate of the manager. 
- Create the **team utility repository**, and add the team-specific utilities to the repository. 
- (Optional) Create **[Azure file storage](https://azure.microsoft.com/services/storage/files/)** to be used to store data assets that can be useful for the entire team. Other team members can mount this shared cloud file store on their analytics desktops.
- (Optional) Mount the Azure file storage to the **Data Science Virtual Machine** (DSVM) of the team lead and add data assets on it.
- Set up the **security control** by adding team members and configure their privileges. 

For detailed step-by-step instructions, see [Team Lead tasks for a data science team](team-data-science-process-team-lead-tasks.md).  


## Project Lead tasks

The following tasks are completed by the Project Lead to adopt the TDSP:

- Create a **project repository** under the team project, and seed it from the Team project template repository. 
- (Optional) Create **Azure file storage** to be used to store data assets of the project. 
- (Optional) Mount the Azure file storage to the **Data Science Virtual Machine** (DSVM) of the Project Lead and add project data assets on it.
- Set up the **security control** by adding project members and configure their privileges. 

For detailed step-by-step instructions, see [Project Lead tasks for a data science team](team-data-science-process-project-lead-tasks.md). 

## Project Individual Contributor tasks

The following tasks are completed by a Project Individual Contributor (usually a Data Scientist) to conduct the data science project using the TDSP:

- Clone the **project repository** set up by the project lead. 
- (Optional) Mount the shared **Azure file storage** of the team and project on their **Data Science Virtual Machine** (DSVM).
- Execute the project. 

 
For detailed step-by-step instructions for onboarding onto a project, see [Project Individual Contributors for a data science team](team-data-science-process-project-ic-tasks.md). 


## Data science project execution
 
By following the relevant set of instructions, data scientists, project lead, and team leads can create work items to track all tasks and stages that a project needs from its beginning to its end. Using git also promotes collaboration among data scientists and ensures that the artifacts generated during project execution are version controlled and shared by all project members.

The instructions provided for project execution have been developed based on the assumption that both work items and project git repositories are on VSTS. Using VSTS for both allows you to link your work items with the Git branches of your project repositories. In this way, you can easily track what has been done for a work item. 

The following figure outlines this workflow for project execution using the TDSP.

![Typical Data Science Project Execution](./media/team-data-science-process-overview-components-roles-tasks/overview-project-execute.png)

The workflow includes steps that can be grouped into three activities:

- Sprint planning (Project Lead)
- Developing artifacts on git branches to address work items (Data Scientist)
- Code review and merging branches with master branches (Project Lead or other team members)

For detailed step-by-step instructions on project execution workflow, see [Execution of data science projects](team-data-science-process-project-execution.md).

<properties
	pageTitle="Execution of data science projects"
	description="How a data scientist can execute a data science project in a trackable, version controlled, and collaborative way."  
	services="machine-learning"
	documentationCenter=""
	authors="bradsev"
	manager="jhubbard"
	editor="cgronlun" />

<tags
	ms.service="machine-learning"
	ms.workload="data-services"
	ms.tgt_pltfrm="na"
	ms.devlang="na"
	ms.topic="article"
	ms.date="09/21/2016"
	ms.author="bradsev;hangzh;"/>


# Execution of data science projects

This document describes how a data scientist can execute a data science project in a systematic, version controlled, and collaborative way within a project team by using the [Team Data Science Process](README.md) (TDSP). The TDSP is a framework developed by Microsoft that provides a structured sequence of activities to execute cloud-based, predictive analytics solutions efficiently. For an outline of the personnel roles, and their associated tasks that are handled by a data science team standardizing on this process, see [Team Data Science Process: roles and tasks](team-data-science-process-roles-tasks.md). 

This topic includes instructions on how to: 

1. do **sprint planning** for work items involved in a project.<br> If you are unfamiliar with sprint planning, you can find details below and general information [here](https://en.wikipedia.org/wiki/Sprint_(software_development) "here"). 
2. **add work items** to sprints.
3. **link the work items with coding activities** tracked by git.
4. do **code review**. 


>[AZURE.NOTE] We outline the steps needed to set up a TDSP team environment using Visual Studio Team Services (VSTS) in the following set of instructions. We specify how to accomplish these tasks with VSTS because that is how we implement TDSP at Microsoft. Items (3) and (4) in the previous list are benefits that you get naturally if you choose to use VSTS. If another code hosting platform is used for your group, the tasks that need to be completed by the team lead generally do not change. But the way to complete these tasks is going to be different. For example, the item in section six, **Link a work item with a git branch**, might not be as easy as it is on VSTS.

The following figure illustrates a typical sprint planning, coding and source-control workflow involved in implementing a data science project:

![1](./media/team-data-science-process-project-execution/project-execution-1-project-execute.png)


1. [Terminology](#Terminology-1)
2. [Sprint planning](#SprintPlanning-2)
3. [Add a Feature](#AddFeature-3)
4. [Add Story under Feature](#AddStoryunderfeature-4)
5. [Add a task to a Story](#AddTaskunderstory-5)
6. [Link a work item with a git branch](#Linkaworkitemwithagitbranch-6)
7. [Work on a branch and commit the changes](#WorkonaBranchandCommittheChanges-7)
8. [Create a pull request on VSTS](#CreateapullrequestonVSTS-8)
9. [Review and merge](#ReviewandMerge-9)
10. [Data Quality Report Utility ](#DataQualityReportUtility-10)
11. [Modeling Utility ](#ModelingUtility-11)
12. [Tracking progress of projects with Power BI dashboards](#PowerBI-12)

##  1. <a name='Terminology-1'></a>Terminology 

In the TDSP sprint planning framework, there are four frequently used types of **work items**: **Feature**, **User Story**, **Task**, and **Bug**. Each team project maintains a single backlog for all work items. There is no backlog at the git repository level under a team project. Here are their definitions:

- **Feature**: A feature corresponds to a project engagement. Different engagements with a client are considered different features. Similarly, it is best to consider different phases of a project with a client as different features. If you choose a schema such as ***ClientName-EngagementName*** to name your features, then you can easily recognize the context of the project/engagement from the names themselves.
- **Story**: Stories are different work items that are needed to complete a feature (project) end-to-end. Examples of stories include:
	- Getting Data 
	- Exploring Data 
	- Generating Features
	- Building Models
	- Operationalizing Models 
	- Retraining Models
- **Task**: Tasks are assignable code or document work items or other activities that need to be done to complete a specific story. For example, tasks in the story *Getting Data* could be:
	-  Getting Credentials of SQL Server 
	-  Uploading Data to SQL Data Warehouse. 
- **Bug**: Bugs usually refer to fixes that are needed for an existing code or document that are done when completing a task. It can escalate to being a story or a task if the bug is caused by missing stages or tasks respectively. 

>[AZURE.NOTE] We are borrowing concepts of features, stories, tasks, and bugs from software code management (SCM) to be used in data science. They might differ slightly from their conventional  SCM definitions.

##  2. <a name='SprintPlanning-2'></a>Sprint planning 

Sprint planning is useful for project prioritization, and resource planning and allocation. Many data scientists are engaged with multiple projects, each of which can take months to complete. Projects often proceed at different paces. On the VSTS server, you can easily create, manage, and track work items in your team project and conduct sprint planning to ensure that your projects are moving forward as expected. 

Follow [this link](https://www.visualstudio.com/en-us/docs/work/scrum/sprint-planning) for the step-by-step instructions on sprint planning in VSTS. 


##  3. <a name='AddFeature-3'></a>Add a Feature  

After your project repository is created under a team project, go to the team **Overview** page and click **Manage work**.

![2](./media/team-data-science-process-project-execution/project-execution-2-sprint-team-overview.png)

To include a feature in the backlog, click **Backlogs** --> **Features** --> **New**, type in the feature **Title** (usually your project name), and then click **Add** .

![3](./media/team-data-science-process-project-execution/project-execution-3-sprint-team-add-work.png)

Double-click the feature you just created. Fill in the descriptions, assign team members for this feature, and set planning parameters for this feature. 

You can also link this feature to the project repository. Click **Add link** under the **Development** section. After you have finished editing the feature, click **Save & Close** to exit.


##  4. <a name='AddStoryunderfeature-4'></a>Add Story under Feature 

Under the feature, stories can be added to describe major steps needed to finish the (feature) project. To add a new story, click the **+** sign to the left of the feature in backlog view.  

![4](./media/team-data-science-process-project-execution/project-execution-4-sprint-add-story.png)

You can edit the details of the story, such as the status, description, comments, planning, and priority In the pop-up window.

![5](./media/team-data-science-process-project-execution/project-execution-5-sprint-edit-story.png)

You can link this story to an existing repository by clicking **+ Add link** under **Development**. 

![6](./media/team-data-science-process-project-execution/project-execution-6-sprint-link-existing-branch.png)


##  5. <a name='AddTaskunderstory-5'></a>Add a task to a story 

Tasks are specific detailed steps that are needed to complete each story. After all tasks of a story are completed, the story should be completed too. 

To add a task to a story, click the **+** sign next to the story item, select **Task**, and then fill in the detailed information of this task in the pop-up window.

![7](./media/team-data-science-process-project-execution/project-execution-7-sprint-add-task.png)

After the features, stories, and tasks are created, you can view them in the **Backlog** or **Board** views to track their status.

![8](./media/team-data-science-process-project-execution/project-execution-8-sprint-backlog-view.png)

![9](./media/team-data-science-process-project-execution/project-execution-9-link-to-a-new-branch.png)


##  6. <a name='Linkaworkitemwithagitbranch-6'></a>Link a work item with a git branch 

VSTS provides a convenient way to connect a work item (a story or task) with a git branch. This enables you to link your story or task directly to the code associated with it. 

To connect a work item to a new branch, double-click a work item, and in the pop-up window, click **Create a new branch** under **+ Add link**.  

![10](./media/team-data-science-process-project-execution/project-execution-10-sprint-board-view.png)

Provide the information for this new branch, such as the branch name, base git repository and the branch. The git repository  chosen must be the repository under the same team project that the work item belongs to. The base branch can be the master branch or some other existing branch.

![11](./media/team-data-science-process-project-execution/project-execution-11-create-a-branch.png)

A good practice is to create a git branch for each story work item. Then, for each task work item, you create a branch based on the story branch. Organizing the branches in this hierarchical way that corresponds to the story-task relationships is helpful when you have multiple people working on different stories of the same project, or you have multiple people working on different tasks of the same story. Conflicts can be minimized when each team member works on a different branch and when each member works on different codes or other artifacts when sharing a branch. 

The following picture depicts the recommended branching strategy for TDSP. You might not need as many branches as are shown here, especially when you only have one or two people working on the same project, or only one person works on all tasks of a story. But separating the development branch from the master branch is always a good practice. This can help prevent the release branch from being interrupted by the development activities. More complete description of git branch model can be found in [A Successful Git Branching Model](http://nvie.com/posts/a-successful-git-branching-model/).

![12](./media/team-data-science-process-project-execution/project-execution-12-git-branches.png)

To switch to the branch that you want to work on, run the following command in a shell command (Windows or Linux). 

	git checkout <branch name>

Changing the *<branch name\>* to **master** switches you back to the **master** branch. After you switch to the working branch, you can start working on that work item, developing the code or documentation artifacts needed to complete the item. 

You can also link a work item to an existing branch. In the **Detail** page of a work item, instead of clicking **Create a new branch**, you click **+ Add link**. Then, select the branch you want to link the work item to. 

![13](./media/team-data-science-process-project-execution/project-execution-13-link-to-an-existing-branch.png)

You can also create a new branch in git bash commands. If <base branch name\> is missing, the <new branch name\> is based on _master_ branch. 
	
	git checkout -b <new branch name> <base branch name>


##  7. <a name='WorkonaBranchandCommittheChanges-7'></a>Work on a branch and commit the changes 

Now suppose you make some change to the *data\_ingestion* branch for the work item, such as adding an R file on the branch in your local machine. You can commit the R file added to the branch for this work item, provided you are in that branch in your Git shell, using the following Git commands:

	git status
	git add .
	git commit -m"added a R scripts"
	git push origin data_ingestion

![14](./media/team-data-science-process-project-execution/project-execution-14-sprint-push-to-branch.png)

##  8. <a name='CreateapullrequestonVSTS-8'></a>Create a pull request on VSTS 

When you are ready after a few commits and pushes, to merge the current branch into its base branch, you can submit a **pull request** on VSTS server. 

Go to the main page of your team project and click **CODE**. Select the branch to be merged and the git repository name that you want to merge the branch into. Then click **Pull Requests**, click **New pull request** to create a pull request review before the work on the branch is merged to its base branch.

![15](./media/team-data-science-process-project-execution/project-execution-15-spring-create-pull-request.png)

Fill in some description about this pull request, add reviewers, and send it out.

![16](./media/team-data-science-process-project-execution/project-execution-16-spring-send-pull-request.png)

##  9. <a name='ReviewandMerge-9'></a>Review and merge 

When the pull request is created, your reviewers get an email notification to review the pull requests. The reviewers need to check whether the changes are working or not and test the changes with the requester if possible. Based on their assessment, the reviewers can approve or reject the pull request. 

![17](./media/team-data-science-process-project-execution/project-execution-17-add_comments.png)

![18](./media/team-data-science-process-project-execution/project-execution-18-spring-approve-pullrequest.png)

After the review is done, the working branch is merged to its base branch by clicking the **Complete** button. You may choose to delete the working branch after it has merged. 

![19](./media/team-data-science-process-project-execution/project-execution-19-spring-complete-pullrequest.png)

Confirm on the top left corner that the request is marked as **COMPLETED**. 

![20](./media/team-data-science-process-project-execution/project-execution-20-spring-merge-pullrequest.png)

When you go back to the repository under **CODE**, you are told that you have been switched to the master branch.

![21](./media/team-data-science-process-project-execution/project-execution-21-spring-branch-deleted.png)

You can also use the following Git commands to merge your working branch to its base branch and delete the working branch after merging:

	git checkout master
	git merge data_ingestion
	git branch -d data_ingestion

![22](./media/team-data-science-process-project-execution/project-execution-22-spring-branch-deleted-commandline.png)


##  10. <a name='DataQualityReportUtility-10'></a>Interactive Data Exploration, Analysis, and Reporting (IDEAR) Utility

This R markdown-based utility provides a flexible and interactive tool to evaluate and explore data sets. Users can quickly generate reports from the data set with minimal coding. Users can click buttons to export the exploration results he sees in the interactive tool to a final report, which can be delivered to clients or used to make decisions on which variables to include in the subsequent modeling step.

At this time, the tool only works on data-frames in memory. A .yaml file is needed to specify the parameters of the data-set to be explored. For more information, see [IDEAR in TDSP Data Science Utilities](https://github.com/Azure/Azure-TDSP-Utilities/tree/master/DataScienceUtilities/DataReport-Utils).


##  11. <a name='ModelingUtility-11'></a>Baseline Modeling and Reporting Utility

This utility provides a customizable, semi-automated tool to perform model creation with hyper-parameter sweeping, to and compare the accuracy of those models. 

The model creation utility is an R markdown file that can be run to produce self-contained html output with a table of contents for easy navigation through its different sections. Three algorithms are executed when the markdown file is run (knit): regularized regression using the glmnet package, random forest using the randomForest package, and boosting trees using the xgboost package). Each of these algorithms produces a trained model. The accuracy of these models is then compared and the relative feature importance plots are reported. Currently, there are two utilities: one is for a binary classification task and one is for a regression task. The primary differences between them is the way control parameters and accuracy metrics are specified for these learning tasks. 

A Yaml file is used to specify:

- the data input (a SQL source or an R-Data file) 
- what portion of the data is used for training and what portion for testing
- which algorithms to run 
- the choice of control parameters for model optimization:
	- cross-validation 
	- bootstrapping
	- folds of cross-validation
- the hyper-parameter sets for each algorithm. 

The number of algorithms, the number of folds for optimization, the hyper-parameters, and the number of hyper-parameter sets to sweep over can also be modified in the Yaml file to run the models quickly. For example, they can be run with a lower number of CV folds, a lower number of parameter sets. They can also be run more comprehensively with a higher number of CV folds or a larger number of parameter sets, if that is warranted.

For more information, see [Automated Modeling and Reporting Utility in TDSP Data Science Utilities](https://github.com/Azure/Azure-TDSP-Utilities/tree/master/DataScienceUtilities/Modeling).


##  12. <a name='PowerBI-12'></a>Tracking progress of projects with Power BI dashboards

Data science group managers, team leads, and project leads need to track the progress of their projects, what work has been done on them and by whom, and remains on the to-do lists. If you are using VSTS, you are able to build Power BI dashboards to track the activities and the work items associated with a Git repository. For more information on how to connect Power BI to Visual Studio Team Services, see [Connect Power BI to Team Services](https://www.visualstudio.com/en-us/docs/report/powerbi/connect-vso-pbi-vs). 

To learn how to create Power BI dashboards and reports to track your Git repository activities and your work items after the data of VSTS is connected to Power BI, see [Create Power BI dashboards and reports](https://www.visualstudio.com/en-us/docs/report/powerbi/report-on-vso-with-power-bi-vs). 

Here are two simple example dashboards that we build to track Git activities and work items. In the first example dashboard, the git commitment activities are listed by different users, on different dates, and on different repositories. You can easily slice and dice to filter the ones that you are interested in.

![23](./media/team-data-science-process-project-execution/project-execution-23-powerbi-git.png)

In the second example dashboard, the work items (stories and tasks) in different iterations are presented. They are grouped by assignees and priority levels, and colored by state.

![24](./media/team-data-science-process-project-execution/project-execution-24-powerbi-workitem.png)

 
