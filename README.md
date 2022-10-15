<<<<<<< HEAD
# confluent-kafka-python


This repo help us to know how to publish and consume data to and from kafka confluent in json format.

Step 1: Create a conda environment
```
conda --version
```

Step2: Create  a conda environment
```
conda create -p venv python==3.8 -y
```

Step3:
```
conda activate venv/
```
Step4:
```
pip install -r requirements.txt
```

#### Download API Key, API secret and Bootstrap server from confluent.io by creating new environment.
* Step1: login to https://confluent.io
* step 2: go to https://confluent.cloud/home
* step 3: click view environments
* step 4: Click add cloud environments and enter a name of your environment
* step 4: Create cluster andthen begin configuration FREE
* step 5: Select GCP=> region Mumbai=> Availability Single Zone => continue
* step 6: Skip payment 
* step 7: Give proper cluster name and launch cluster   
* step 8: Click API Keys(left middle of screen)=> Create key => Gloable Access => Add description => dowload and continue
* step 9: You will have file with API Key, API secret and Bootstrap server.

#### Create kafka topic
* Step 1: Click API Keys(left middle of screen)=> Create topic => enter kafka topic name and partitions => click create topic

#### Enable schema registry and Add key
* step 1: click on HOME=> View environment => click on your environment => click Enable Now (right middle under Stream Governance package)
* step 2: Begin configuration FREE
* step 3: Choose AWS and put nearest region and click enable
* step 4: You will see Stream Governance API at right bottom=>just copy ENDPOINT_SCHEMA_URL for future use then => click Add key(under Credentials) => Create key => download the key
* step 5: You will have file with API Key, API secret.

#### how to setup environments variables in linux
* Step 1: open file name .bashrc which is in home directory
```
nano ~/.bashrc
```
* Step2: Write environment variable under below lines of .bashrc
```
unset __conda_setup
# <<< conda initialize <<<
```
* Step3: Below are the environment variable we have to write(look at src/kafka_config/__init__.py)
```
export API_KEY==<<<<>>>>
export ENDPOINT_SCHEMA_URL=<<<<>>>>
export API_SECRET_KEY==<<<<>>>>
export BOOTSTRAP_SERVER==<<<<>>>>
export SECURITY_PROTOCOL=SASL_SSL
export SSL_MACHENISM=PLAIN
export SCHEMA_REGISTRY_API_KEY==<<<<>>>>
export SCHEMA_REGISTRY_API_SECRET==<<<<>>>>
```
* Step4: After saving /bashrc, run below command(optionla)
```
source ~/.bashrc
```
* Step5: We can check if we can fetch enviroment variables
```
echo $API_KEY
```
=====
