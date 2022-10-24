# PyWebIO Secure

A fork of pywebio 1.7 that supports HTTPS. Bring your own cert, or automatically generate a new TLS 1.3 cert.

## Credit

Credit goes to PyWebIO's creator for the source code. This project is based on pywebio 1.7 with changes and additions made to add a critical security feature.

## New Features

- Automatically generate TLS 1.3 certs using openSSL.
- Supports BYOC (Bring Your Own Cert).


## Requirements

If you are not providing your own cert, openssl is required. 
```bash
apt-get install openssl -y
```


## Installation

- Download the two folders in this repo. 
- Copy them both to your python packages folder.


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

start_server(test_screen, port=443, debug=True)
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

start_server(test_screen, port=443, debug=True, byoc=["/home/sandbox/Desktop/cert.pem", "/home/sandbox/Desktop/key.pem"])
```

## Additional Info
All other functionality is the same as in pywebio 1.7. 
Reference https://pywebio.readthedocs.io/ for further documentation.
