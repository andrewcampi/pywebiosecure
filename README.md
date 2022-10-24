# pywebiosecure
A fork of pywebio that supports HTTPS


## Features：

- Automatically generate TLS 1.3 certs using openSSL.
- Supports BYOC (Bring Your Own Cert).


## Requirements
If you are not providing your own cert, openssl is required. 
```bash
apt-get install openssl -y
```


## Installation

```bash
pip3 install pywebiosecure
```


## Example code (Auto generate cert)

```bash
from pywebiosecure.session import download, info
from pywebiosecure.output import *
from pywebiosecure.input import *
from pywebiosecure.pin import *
from pywebiosecure.platform.django import start_server

def test_screen():
	clear()
	put_text("Got here!")
	print("Got here!")

start_server(test_screen, port=8585, debug=True)
```

## Example code (BYOC)
```bash
from pywebiosecure.session import download, info
from pywebiosecure.output import *
from pywebiosecure.input import *
from pywebiosecure.pin import *
from pywebiosecure.platform.django import start_server

def test_screen():
	clear()
	put_text("Got here!")
	print("Got here!")

start_server(test_screen, port=8585, debug=True, byoc=["/home/sandbox/Desktop/cert.pem", "/home/sandbox/Desktop/key.pem"])
```
