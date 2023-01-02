# Ansible playbook to install and setup all the stuff on my home envrionment
# Setup env:
install the following pes on your system:
ansible, helm
kubeconfig is seted in your home folder
vault pass is in password safe
python3 -m pip install -r ./ansible/requirements.txt
ansible-galaxy install -r ansible/requirements.yaml

# Running:
ansible-playbook ./ansible/playbook.yaml --ask-vault-pass

 # Encrypt/Decrypt vaultes files
ansible-vault decrypt ansible/roles/foundry/vars/gyongy-vault.yaml ansible/roles/foundry/vars/bazs-vault.yaml ansible/roles/tls-secret/vars/dotfun_vault.yaml
ansible-vault encrypt ansible/roles/foundry/vars/gyongy-vault.yaml ansible/roles/foundry/vars/bazs-vault.yaml ansible/roles/tls-secret/vars/dotfun_vault.yaml

# Encrypt specific var:
ansible-vault encrypt_string  'secret_here' --name 'varname_here'

# Create basic auth token
USER=klucsik; PASSWORD=<PASSWORD_HERE>; echo "${USER}:$(openssl passwd -stdin -apr1 <<< ${PASSWORD})" >> auth

# Changing the tls:
sudo certbot certonly --manual -d *.klucsik.fun
ansible-vault decrypt ansible/roles/tls-secret/vars/dotfun_vault.yaml
copy paste
ansible-vault encrypt ansible/roles/tls-secret/vars/dotfun_vault.yaml

hacks:
2022.11.27.: The cluster reinstall was not sucessfull as calico coming with microk8s not compatbile with OS ipset. upgraded cailco version in the deployment.