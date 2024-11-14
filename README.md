# Ex01 Developing a Simple Webserver
## Data:
## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation

### Step 2:
Design of webserver workflow

### Step 3:
Implementation using Python code

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver


## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler

content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1><u>Languages used in Web Development</u></h1>
<ul>
<li>HTML</li>
<li>CSS</li>
<li>JavaScript</li>
<li>Bootstrap</li>
</ul>
</body>
</html>
"""

class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Request received")
        self.send_response(200)
        self.send_header('Content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())

# Try changing to port 8080 or any other port if needed
server_address = ('', 8080)
httpd = HTTPServer(server_address, myhandler)
print("My webserver is running...")
httpd.serve_forever()

```


## OUTPUT:
![image](https://github.com/user-attachments/assets/aaf1df5c-b1a5-4fa6-b58e-7656f8c7f1bf)

![image](https://github.com/user-attachments/assets/3dd6004a-7151-434e-8019-f32f0bde764f)



## RESULT:
The program for implementing simple webserver is executed successfully.
