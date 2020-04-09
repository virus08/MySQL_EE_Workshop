# Setting up OCI CLI
To use OCI, it is handy to set up the OCI CLI to work directly with OCI
You need to have Python 3.X, PIP installed before you can get OCI CLI configured
## Install Python 3 and PIP
On Windows, just download and install Python and PIP
Create a virtualenv so that you can install OCI CLI in the virtualenv
```
python install pip
pip install virtualenv
virtualenv my-venv  ## you can use this command as well: python -m venv %systemdrive%%homepath%\my-venv
cd my-venv
cd Scripts
activate
```
(my-venv)

## Install OCI-CLI
Download the OCI CLI package from https://github.com/oracle/oci-cli/releases
Unzip and install the OCI CLI in your virtualenv

(my-venv)
```
pip install oci_cli-2.9.8-py2.py3-none-any.whl
```

## Configuring OCI CLI environment
First, generate public/private key using puttygen
1. Select **SSH-2 RSA** as default key type, **2048** bits, hit **Generate** key
2. Save the Private Key in **ppk** format (proprietary putty format)
3. Save the Public Key in **pub** format (the public key format is NOT the **rsa public key** needed)
and convert the ssh public key format to rsa public key
```
ssh-keygen -f xxx.pub -e -i pem
-----BEGIN RSA PUBLIC KEY-----
9999999999999999999999999dsafsdfasfwerwe99==
-----END RSA PUBLIC KEY-----
```

Next, upload the **Public Key** to OCI as part of your user profile settings

You are now ready to config OCI configuration (you need to have your user-id, tenancy-id, region, public/private keys)
(my-venv)
```
C:\Users\rkuan\my-venv\Scripts>oci setup config
oci os ns get
```

You should be able to connect to OCI once you have configured the right settings

