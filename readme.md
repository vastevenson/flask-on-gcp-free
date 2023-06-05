### Flask App on Google App Engine (GAE)

#### Set up locally
* `python -m venv venv` to set up a new virtual env locally
* Run cmd `source env/bin/activate` to active the virtual env (mac) from project dir. 
* `pip install -r requirements.txt` to install the requirements for the project locally in the venv.
* In the env, run the cmd `python main.py` to start the flask web server locally, it should be running at http://localhost:5000/
* When you want to end the server, run cmd: `Control + C` to stop.
* 
### Installing gcloud on Mac
* gcloud is needed to interact with GCP's services
* Easiest way to install is with Homebrew (brew): `brew install --cask google-cloud-sdk`
* After successful install, run cmd: `gcloud init` to authenticate your account with GCP's local cli tool

### Deploying the app to GAE 
* `gcloud config set project vs-flask-demo` create a new project id in your GCP account for this service 
* `gcloud projects create vs-flask-demo --set-as-default`  set this project as the default project for gcloud 
* `gcloud app deploy` deploy the service
* View your app on the url or run cmd: `gcloud app browse`

### Deleting project when done
To avoid getting billed, run cmd: `gcloud projects delete vs-flask-demo` when you're done. 

### Free tier limits as of 2021 (check GCP site for updated free tier limits)
Instance Hours: The free tier typically provides 28 instance hours per day for the App Engine standard environment and 9 instance hours per day for the flexible environment. Instance hours refer to the time your application spends running on an instance.

Outbound Data: The free tier usually includes a certain amount of free outbound data transfer per month. The exact limit may vary depending on the region. For example, as of my knowledge cutoff, the free tier provides 1 GB of outbound data per day for the App Engine standard environment.

Storage: The free tier generally offers a limited amount of storage space for your application's data. For example, you may have up to 1 GB of Cloud Datastore storage and 5 GB of Cloud Storage storage.

Requests and Bandwidth: There are typically limitations on the number of requests and bandwidth available for free. These limits can vary depending on the specific services and regions. For example, as of my knowledge cutoff, the free tier provides 5 GB of outgoing network bandwidth per day for the App Engine standard environment.