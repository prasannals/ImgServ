# ImgServ

Library which helps with sending and receiving images. Developed to help people focus on the image processing more without having to worry about the networking aspects.

## Installation

pip install img_serv

## Usage

### Server Side
```
from img_serv.server import ImgServ

def handler(image):
    # process image
    return 'Image recieved'  #or anything else that you would like to return to client

im = ImgServ(handler, host = '0.0.0.0', port_number = 12222, save_loc = '.', incoming_fname = 'image.jpg', image_prefix = 'img_', image_format = '.jpg', datetime_delimiter = '_')

im.run()
```

### Client Side

#### Desktop Client
```
from img_serv.desktop_client import DesktopClient

# without handler
client = DesktopClient(filename = 'image.jpg', location = 'images', ip = 'localhost', port = 12222, exitKey = 'x', captureKey = 'c', windowTitle = 'ImgServ DesktopClient')
client.run()

# with handler to handle response

def handler(response):
  # response is Flask Response object
  pass

client = DesktopClient(handler = handler)
client.run()
```

#### RaspberryPi Client
```
from img_serv.raspi_client import RaspiClient

# without handler
client = RaspiClient(filename = 'image.jpg', location = 'images', ip = 'localhost', port = 12222, exitKey = 'x', captureKey = 'c', windowTitle = 'ImgServ DesktopClient')
client.run()

# with handler to handle response

def handler(response):
  # response is Flask Response object
  pass

client = RaspiClient(handler = handler)
client.run()
```
