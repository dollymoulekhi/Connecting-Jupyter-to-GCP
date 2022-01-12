# Connecting-Jupyter-to-GCP

```
!pip install google

!pip install google-cloud-storage

```

```
from google.cloud.storage.client import Client

from google.cloud.storage.bucket import Bucket

from google.cloud.storage.blob import Blob

from google.oauth2.service_account import Credentials

```


```
credentials = Credentials.from_service_account_file('projectcredentials.json')


client = Client(project='project_name', credentials=credentials)

bucket = Bucket(client=client, name='name of the bucket')

blob = Blob(name='file_location_withname', bucket=bucket)

```


## For loop for getting multiple files while iterating

```
for i in range(0,1000):
    x= '000000000000'
    x=x[:-(len(str(i)))
    x=x+(str(i))
    blob.download_to_filename('filename'+str(x)+'.csv')
    
```
