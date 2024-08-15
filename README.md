I . ((Install AWS CLI))

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


