# ImgServ

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
