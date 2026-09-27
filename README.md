# Homelab Docker

## Create SOPS and Age 

### Create private key and see public key
age-keygen -o key.txt

mkdir -p ~/.config/sops/age/
mv key.txt ~/.config/sops/age/keys.txt

echo 'export SOPS_AGE_KEY_FILE=$HOME/.config/sops/age/keys.txt' >> ~/.bashrc
source ~/.bashrc

### Read things, for example
ops --input-type dotenv --output-type dotenv secrets/audiomuse.env.sops