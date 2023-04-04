# Mlops-classification-AWS
# Project: An end-to-end classification model for determining the quality of red wine + Sagemaker integration
## ✨ Project information:
This project aims to build a Red Wine quality classification model using two datasets related to red and white variants of the Portuguese "Vinho Verde" wine. These datasets consist of physicochemical (inputs) and sensory (output) variables, with the output variable being the quality score between 0 and 10. The classes are ordered and not balanced, with much more normal wines than excellent or poor ones.

To deploy an end-to-end MLOps pipeline for this project, AWS will be used for S3 storage of raw data, Mysql server for storing model artifacts, mlflow for tracking experiments, and Terraform for deploying and destroying infrastructure automatically. The pipeline will include data preprocessing, feature engineering, model training, and deployment. The trained model will be saved in the Mysql server and deployed for inference. The pipeline will be monitored using mlflow to ensure the performance of the model remains within the acceptable range.

## 📚 Libraries used :
* Scikit-learn
* Pandas
* Numpy
* mlflow

### 🔥 Technologies Used:
``` 
1. Python 
2. shell scripting 
3. aws cloud Provider
4. Terraform
```

## 🔌 Infrastructure:
```
1. AWS S3, Mysql server
2. GitHub
3. Docker
```

## 👷 Initial Setup: 
```commandline
conda create --prefix ./env python=3.9
conda activate ./env 
pip install -r requirements.txt
dvc init
```

## MLFlow provides explicit AWS SageMaker support in its operationalization code.
```
create --prefix ./env python=3.8 -y && conda activate ./env 
```

### Run 2-3 times with different alpha and li ratio
```
python main.py alpha l1_ratio
```
### To See logs 
```commandline
mlflow ui
```
### PREREQUISITES 
1. Install AWS CLI 
2. Open Cmd : aws configure
3. Paste Public key , private key and Region
4. Run below command

### Permissions 
1. AmazonEC2ContainerRegistryFullAccess
2. AmazonS3FullAccess
3. EC2InstanceProfileForImageBuilderECRContainerBuilds
4. AWSAppRunnerServicePolicyForECRAccess

## Create Image and Upload on docker 
```
mlflow sagemaker build-and-push-container
```
## Run Server
```
mlflow server
--backend-store-uri mysql://admin:pass@endpoint/DB-name
--default-artifact-root ./artifacts
--host 127.0.0.1
-p 5000
```


### Send Ml-runs on Aws-S3 Bucket
```commandline
python utils/sagemaker_integration.py
```


### To build and Push Container
```commandline
mlflow sagemaker build-and-push-container
```


## Check Errors If occurred try:
```
docker.errors.DockerException: Install pypiwin32 package to enable npipe:// support
Solution : Instead of pip install pypiwin32  Try : conda install -c anaconda pywin32
```


## Conclusion<a id='conclusion-'></a>
This project is production ready to be used for the similar use cases and it will provide the automated and orchesrated production ready pipelines(Training & Serving)
#### **Thanks for taking a look at this project. If you find it valuable, kindly rate it by clicking the star icon. Your support is highly appreciated! 😊🙏⭐**<br><br>

#### **📃 License**
MIT license ©
My Website **[``website``](https://)** <br>
Let's connect on **[``LinkedIn``](https://www.linkedin.com/in/hamed-mehrabi/)** <br>


