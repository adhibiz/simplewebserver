# EX01 Developing a Simple Webserver
## Date:

## AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
### Index.html
~~~
<!DOCTYPE html>
<html>
  <head>
    <title>System Configuration</title>
  </head>
  <body>
    <h1>Laptop Configuration Details</h1>
    <ul>
      <li>System: {{ system_info.system }}</li>
      <li>Node: {{ system_info.node }}</li>
      <li>Release: {{ system_info.release }}</li>
      <li>Version: {{ system_info.version }}</li>
      <li>Machine: {{ system_info.machine }}</li>
      <li>Processor: {{ system_info.processor }}</li>
    </ul>
  </body>
</html>
~~~
### app.py
~~~
from flask import Flask, render_template
import platform

app = Flask(__name__)

@app.route('/')
def home():
    # Get system details
    system_info = {
        'system': platform.system(),
        'node': platform.node(),
        'release': platform.release(),
        'version': platform.version(),
        'machine': platform.machine(),
        'processor': platform.processor()
    }
    # Render HTML with system details
    return render_template('index.html', system_info=system_info)

if __name__ == '__main__':
    app.run(debug=True)

~~~

## OUTPUT:
### Index
![image](https://github.com/user-attachments/assets/b3382847-9c96-46cb-8127-98aab8d41572)

### app 
![image](https://github.com/user-attachments/assets/35319c3d-f0fa-4095-bd1a-6b04ce4416f0)



## RESULT:
The program for implementing simple webserver is executed successfully.
