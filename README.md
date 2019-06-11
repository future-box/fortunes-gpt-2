# Generate fortunes using OpenAI gpt-2

 larger models, we have [released a dataset](https://github.com/openai/gpt-2-output-dataset) for researchers to study their behaviors.

See more details on OpenAI blog (https://blog.openai.com/better-language-models/). Original README.md is based on GPT2-README.md

## Notebook

```bash
jupyter-notebook futurebox-notebook.ipynb
```

### Dataset 

Download the dataset and store in S3. 

### AWS IAM Role 

Create new IAM role, AWS Permissions: Sagem

### AWS Sagemaker

Recommended GPU instance type ```ml.p2.xlarge ```

Create new code repository in Sagemaker

```bash
aws sagemaker create-code-repository \
    --code-repository-name "t04glovern-gpt-2" \
    --git-config '{"Branch":"master", "RepositoryUrl" : "https://github.com/t04glovern/fbmsg-analysis-gpt-2" }'
```

### Work with us

Please [let us know](mailto:languagequestions@openai.com) if you’re doing interesting research with or working on applications of GPT-2!  We’re especially interested in hearing from and potentially working with those who are studying
- Potential malicious use cases and defenses against them (e.g. the detectability of synthetic text)
- The extent of problematic content (e.g. bias) being baked into the models and effective mitigations
