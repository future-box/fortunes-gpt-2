# Generate fortunes using OpenAI gpt-2

Generate fortunes using OpenAI GPT-2 training model with training performed on a Sagemaker GPU instance

See more details on OpenAI blog (https://blog.openai.com/better-language-models/). 

Original README.md is based on GPT2-README.md

## Notebook

```bash
jupyter-notebook futurebox-notebook.ipynb
```

### Dataset 

Download the dataset and store in S3. 

### AWS IAM Role 

Create new IAM role with AWS service permissions: ```AmazonSageMakerFullAccess ```

After creation attach a ```AdministratorAccess ``` policy (only required while training)

### AWS Sagemaker

Recommended GPU instance type ```ml.p2.xlarge ```

Create new code repository in Sagemaker

```bash
aws sagemaker create-code-repository \
    --code-repository-name "ai-fortune-teller" \
    --git-config '{"Branch":"finetuning", "RepositoryUrl" : "https://github.com/future-box/fortunes-gpt-2" }'
```

Create Sagemaker notebook instance

```bash
aws sagemaker create-notebook-instance \
    --notebook-instance-name "fortunes-gpt-2" \
    --instance-type "ml.p2.xlarge" \
    --role-arn "COPY/PASTE your ARN from IAM role created above" \
    --default-code-repository "ai-fortune-teller"
```

### Run notebook

Open Sagemaker notebook in Jupyter or JupyterLab and open file ```futurebox-notebook.ipynb```

Updated your bucket folder / file path in notebook file

Run


