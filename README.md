# Installing the CDE CLI

This tutorial provides a reference for installing the CDE CLI with an automated script.


### Why the CDE CLI

CDE provides you with a rich UI to create, monitor, troubleshoot Spark and Airflow jobs, and more. While this has its advantages, when it comes to creating and executing large amounts of CDE Jobs in Production scenarios the CDE CLI and API offer some advantages and are thus recommended options over the UI.

You can use the CDE CLI or API to execute Spark and Airflow jobs remotely. In general, the CDE CLI is recommended when running spark submits from a local computer. The API is instead recommended when integrating CDE Jobs with 3rd party orchestration systems.

For example you can use GitLab CI to build CDE Pipelines across multiple Virtual Clusters. For a detailed example, please reference [GitLab2CDE](https://github.com/pdefusco/Gitlab2CDE).


### Manual CLI Installation

You can download the CDE CLI to your local machine following the instructions provided in the [official documentation](https://docs.cloudera.com/data-engineering/cloud/cli-access/topics/cde-cli.html).


### Automated CLI Installation

Alternatively, you can use the "00_cde_cli_install.py" automation script located in this GitHub Repository. This will install the CDE CLI in your local machine if you have a Mac.

##### Requirements

To use the install script you will need:

* A CDE Virtual Cluster in Azure, AWS, RedHat OCP or Cloudera ECS.
* Your CDE Virtual Cluster Jobs API URL and CDP Workload User. The CDP Workload Password is not necessary yet as it will be required when you submit your jobs via the CLI.
* This script has been tested on a Mac.

##### Automated CLI Installation Steps

First, clone this Github Repository.

```
cd ~/Documents
mkdir cde_cli_install
cd cde_cli_install
git clone https://github.com/pdefusco/CDE_CLI_Install.git
```

Then, create a Python virtual environment and install the requirements.

```
#Create
python3 -m venv venv

#Activate
source venv/bin/activate

#Install requirements
pip install -r requirements.txt #Optionally use pip3 install
```

Next, execute the script with the following commands:

```
python ~/Documents/cde_cli_install/cde_cli_install.py JOBS_API_URL CDP_WORKLOAD_USER
```

Finally, test the installation with a simple CLI command:

```
cde --help
```


### Next Steps

If you are exploring CDE you may find the following tutorials relevant:

* [Spark 3 & Iceberg](https://github.com/pdefusco/Spark3_Iceberg_CML): A quick intro of Time Travel Capabilities with Spark 3.

* [Simple Intro to the CDE CLI](https://github.com/pdefusco/CDE_CLI_Simple): An introduction to the CDE CLI for the CDE beginner.

* [CDE CLI Demo](https://github.com/pdefusco/CDE_CLI_demo): A more advanced CDE CLI reference with additional details for the CDE user who wants to move beyond the basics.

* [CDE Resource 2 ADLS](https://github.com/pdefusco/CDEResource2ADLS): An example integration between ADLS and CDE Resource. This pattern is applicable to AWS S3 as well and can be used to pass execution scripts, dependencies, and virtually any file from CDE to 3rd party systems and viceversa.

* [Using CDE Airflow](https://github.com/pdefusco/Using_CDE_Airflow): A guide to Airflow in CDE including examples to integrate with 3rd party systems via Airflow Operators such as BashOperator, HttpOperator, PythonOperator, and more.

* [GitLab2CDE](https://github.com/pdefusco/Gitlab2CDE): a CI/CD pipeline to orchestrate Cross-Cluster Workflows for Hybrid/Multicloud Data Engineering.

* [CML2CDE](https://github.com/pdefusco/cml2cde_api_example): an API to create and orchestrate CDE Jobs from any Python based environment including CML. Relevant for ML Ops or any Python Users who want to leverage the power of Spark in CDE via Python requests.

* [Postman2CDE](https://github.com/pdefusco/Postman2CDE): An example of the Postman API to bootstrap CDE Services with the CDE API.

* [Oozie2CDEAirflow API](https://github.com/pdefusco/Oozie2CDE_Migration): An API to programmatically convert Oozie workflows and dependencies into CDE Airflow and CDE Jobs. This API is designed to easily migrate from Oozie to CDE Airflow and not just Open Source Airflow.

For more information on the Cloudera Data Platform and its form factors please visit [this site](https://docs.cloudera.com/).

For more information on migrating Spark jobs to CDE, please reference [this guide](https://docs.cloudera.com/cdp-private-cloud-upgrade/latest/cdppvc-data-migration-spark/topics/cdp-migration-spark-cdp-cde.html).

If you have any questions about CML or would like to see a demo, please reach out to your Cloudera Account Team or send a message [through this portal](https://www.cloudera.com/contact-sales.html) and we will be in contact with you soon.

![alt text](img/cde_thankyou.png)
