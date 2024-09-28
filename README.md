# Taxi Data Analysis with local LLMs
This repository showcases a personal project where I deploy a local Large Language Model (LLM) using OpenWebUI to perform data analysis on the NYC Taxi dataset.

## Setup 
To easily download and manage LLMs locally, install Ollama on Mac, using the following 

```
brew install ollama
```
This will install the formula by default, which is what we need. To start it, run:

```
brew services start ollama
```

Check if it is running by executing:

```
ollama --version
```
To download a model, say llama 3.1, run: 

```
ollama pull llama3.1
```
This is will download the 8B parameter model. To run that model within your shell, run:

```
ollama run llama3.1
``` 
To stop it, simply type `/bye`. 

In order to have a web interface for using the LLM, we start by cloning the OpenWebUI repository: 
```
git clone https://github.com/open-webui/open-webui.git
```

The frontend is written in Javascript while the backend is written in Python. For the backend, I recommend using conda to setup a new environment by running:

```
conda create --name openwebui python=3.11 
```
Activate the environment by running:

```
conda activate openwebui
```

Then go to the backend folder within the openwebui repository and run:

```
pip install -r requirements.txt -U 
```

Next we node for which we use nvm to manage the node environment. Since the requirements for openwebui are node:>=18.13.0 <=21.x.x and npm:>=6.0.0, we use version 20 by simply running 

```
nvm install 20
```
Check the version by running: 

```
node --version
```

Next, go to the parent directory and run:

```
npm install 
```
and 
```
npm run build
```

Then go back to the backend subdirectory and run 
```
bash start.sh 
```

Now we are ready to run the LLM on a web interface. To access it, open the browser of your choice and go to `localhost:8080/auth/` and you will be prompted to sign up there. The credentials stay local so you can enter whatever you want. The web interface allows you to download models, select a model and chat with it. You can also turn on the ability to browse the web by turning it on in the admin settings. 
