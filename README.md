# How-to Guide

## Smoke test our image locally

```bash
docker build -t foo . && docker run -p 30001:30000 foo
```

Open any browser and access this address `http://localhost:30001/docs` and play around with the Swagger UI.

Another way to play with your API is by using the library `requests`

```bash
pip install -r requirements_dev.txt
cd examples/
python predict.py
```

## Prepare for deployment on GCP

### Set up Jenkins

Please take a look at the `README.md` of the folder `ansible/`.

### Set up pre-commit

- Run the following command to ask `pre-commit` to run on every commit
  ```shell
  pre-commit install
  ```
- Ask `pre-commit` to run on all files
  ```shell
  pre-commit run --all-files
  ```
