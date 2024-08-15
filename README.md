take an ec2

I . ((Install AWS CLI))

(Install unzip - 1 and AWS CLI - 3)

sudo apt install unzip

curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"

unzip awscliv2.zip

sudo ./aws/install

aws --version (check)

II . ((Install Terraform - 6))

1. sudo apt-get update && sudo apt-get install -y gnupg software-properties-common

2. wget -O- https://apt.releases.hashicorp.com/gpg | \
gpg --dearmor | \
sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg > /dev/null

3. gpg --no-default-keyring \
--keyring /usr/share/keyrings/hashicorp-archive-keyring.gpg \
--fingerprint

4. echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
https://apt.releases.hashicorp.com $(lsb_release -cs) main" | \
sudo tee /etc/apt/sources.list.d/hashicorp.list

5. sudo apt update

6. sudo apt-get install terraform

terraform -help (check)

III. ((AWS Configure - provide access keys))

aws iam list-users (check)

IV. ((Execute))

git clone https://github.com/pvkraja227/EKS_Terraform.git

terraform init

terraform plan

terraform apply --auto-approve (takes 15 min) - check all tabs - compute/nodegroups - 2 desired, but could not see the nodes

eks/cluster/name/access/create access entry/IAM Principal ARN/arn:aws:iam:7869..:root/next/access policy/amazoneksclusteradminpolicy/add policy/next/create

cluster/name/compute/nodes - 2 (t3.med)

ec2: aws eks update-kubeconfig --name xxxxx --region yyyyy (kubectl is configured)

kubectl get nodes

terraform destroy



