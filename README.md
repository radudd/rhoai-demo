
1. Show the platform
 . Explain projects
 . Explain workspaces
 . Explain datasources
 . Explain pipelines
 . Explain model serving

2. Deploy Minio

```
oc apply -f https://raw.githubusercontent.com/RedHatQuickCourses/rhods-qc-apps/main/4.rhods-deploy/chapter2/minio.yml -n object-datastore 
```

- decide between diabetes and credit card

3. Upload dataset to a bucket in minio. Call it `model-data`

Download first [credit card dataset](https://drive.google.com/file/d/1Gd-ENv1SdqcXYFf81KKIWAsSFwe0Z6ch/view?usp=sharing)

or this for [diabetes](https://raw.githubusercontent.com/RedHatQuickCourses/rhods-qc-apps/main/3.create-model/pytorch-lab/data/diabetes.csv)

Upload to S3 : drag and drop

4. Create a Data connection for being able to collect the model.

```
key_id = os.getenv("AWS_ACCESS_KEY_ID")
secret_key = os.getenv("AWS_SECRET_ACCESS_KEY")
endpoint = os.getenv("AWS_S3_ENDPOINT")
bucket_name = os.getenv("AWS_S3_BUCKET")

s3 = boto3.client(
    "s3",
    aws_access_key_id=key_id,
    aws_secret_access_key=secret_key,
    endpoint_url=endpoint,
    use_ssl=True
)

s3.download_file(bucket_name, s3_data_path, "data/creditcard.csv")
```


5. Open Jupyter and train the model

[Docs](https://github.com/RedHatQuickCourses/rhods-qc-apps/tree/main/7.hands-on-lab)

Create a workbench using `Jupyter TensorFlow`` image

Clone this repo https://github.com/RedHatQuickCourses/rhods-qc-apps 

Run the stuff `7.Solution`

6. Serve the model

7. Test the model from a Jupyter notebook with an API call
