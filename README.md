# PyWebIO Secure

A fork of pywebio 1.7 that supports HTTPS

## Credit

Credit goes to PyWebIO's creator for the source code. I made some changes to a few files to add this critical security feature.

## Additional Features

- Automatically generate TLS 1.3 certs using openSSL.
- Supports BYOC (Bring Your Own Cert).


## Requirements

If you are not providing your own cert, openssl is required. 
```bash
apt-get install openssl -y
```


## Installation

- Download the two folders in this repo. 
- Copy them both to your python library folder.


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
