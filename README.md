# wildrydes

# Approach 2 Deploying a serverless App by using AWS CodeCommit and AWS Amplify

## Terminal Commands

### Make a directory for this approach.

```
mkdir sample_dir
```

```
cd sample_dir
```

### Installation and Configuration

```
pip3 install aws-shell git-remote-codecommit
```

```
aws configure
```

### Provide you own Access Key/Secret and desire region (example below)

<img width="810" alt="Screenshot 2023-10-22 at 8 54 25 PM" src="https://github.com/XingzheZhao/cmpe272-hw4/assets/98489037/2549f29d-9279-46e6-941a-683617223222">

### Starting

Create a repository

```
aws codecommit create-repository --repository-name <your_desire_repository_name>
```

Clone an existing GitHub repository

```
git clone git@github.com:aws-samples/aws-serverless-webapp-workshop.git
```

```    
cd aws-serverless-webapp-workshop
```

Split out a project

```
git subtree split -P resources/code/WildRydesVue -b <your_desire_branch_name>
```

```
cd ..
```

```
mkdir <new_directory_name>
```

```
cd <new_directory_name>
```

```
git init
```

```
git pull ../aws-serverless-webapp-workshop <your_desire_branch_name>
```

```
git remote add origin codecommit://<your_desire_repository_name>
```

```
git push -u origin main
```

```
cd ..
```

### After Pushing
Login to your AWS account that connect to the access key and access secret, then visit the CodeCommit page to check if the project is successfully pushed or not. If successful, host your web app.

## Reference

- https://github.com/aws-samples/aws-serverless-webapp-workshop
