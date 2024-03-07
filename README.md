# DEMO RHOAI

1. Deploy Minio

```
oc apply -f https://raw.githubusercontent.com/RedHatQuickCourses/rhods-qc-apps/main/4.rhods-deploy/chapter2/minio.yml -n object-datastore 
```

2. Create one bucket in Minio, call it `demo`. Upload dataset to the `data/diabetes.csv` in Minio bucket.

The dataset to upload resides in `data/folder`.

3. In OpenShift AI, create a Data connection for being able to collect the model.

4. In OpneShift AI, create a new Workbench based on PyTorch.

4. Open Jupyter, create, train and export the model to S3

[Docs](https://github.com/radudd/rhoai-demo)

5. In OpenShift AI, serve the model

6. Test the model from a Jupyter notebook with an API call
