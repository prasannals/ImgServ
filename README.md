# ImgServ

Library which helps with sending and receiving images. Developed to help people focus on the image processing more without having to worry about the networking aspects.

## Usage

### Server Side
```
from server import ImgServ

def handler(image):
    # process image
    return 'Image recieved'  #or anything else that you would like to return to client

im = ImgServ(handler)
im.run()
```

### Client Side 

#### Desktop Client 
```
client = DesktopClient(filename = 'image.jpg', location = 'images', ip = 'localhost', port = 12222, exitKey = 'x', captureKey = 'c', windowTitle = 'ImgServ DesktopClient')

client.start()
```

#### RaspberryPi Client 
```
client = RaspiClient(filename = 'image.jpg', location = 'images', ip = 'localhost', port = 12222, exitKey = 'x', captureKey = 'c', windowTitle = 'ImgServ DesktopClient')

client.start()
```
