# EX01 Developing a Simple Webserver
## Date: 26.09.2024

## AIM:
To develop a simple webserver to display the configuration details of my laptop.

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
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = '''
<!DOCTYPE html>
<html>
  <head>
    <title>sruthi 212223100061</title>
  </head>
  <body>
      <h1>My Laptop Configuration</h1>
      <h2>sruthi 212223100061</h2>
      <br>
      <table align="center" border="2" cellpadding="5">
        <tr>
          <th>Specifications</th>
          <th>Details</th>
        </tr>
        <tr>
          <td>Brand</td>
          <td>Lenovo</td>
        </tr>
        <tr>
          <td>Model Name</td>
          <td>Galaxy Book 2</td>
        </tr>
        <tr>
          <td>Screen Size</td>
          <td>16</td>
        </tr>
        <tr>
          <td>Harddisk Size</td>
          <td>256 GB</td>
        </tr>
        <tr>
          <td>CPU Model</td>
          <td>Others</td>
        </tr>
        <tr>
          <td>RAM Memory Installed Size</td>
          <td>9 GB</td>
        </tr>
        <tr>
          <td>Operating System</td>
          <td>Windows 11 Home</td>
        </tr>
        <tr>
          <td>Special Feature</td>
          <td>Facelock Reader</td>
        </tr>
        <tr>
          <td>Graphics Card Description</td>
          <td>Integrated</td>
        </tr>
      </table>
  </body>
</html>
'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("GET request received")
        self.send_response(200)
        self.send_header("Content-Type", "text/html")
        self.end_headers()
        self.wfile.write(content.encode())

print("This is a web server")
server_address = ('', 8000)
httpd = HTTPServer(server_address, MyServer)
httpd.serve_forever()
```
## OUTPUT:
TERMINAL:

![image](https://github.com/user-attachments/assets/98408244-2bcc-49b7-bc8a-21c8d9fe5cf1)
Server:

![image](https://github.com/user-attachments/assets/da60c79c-0c78-4396-a0ff-6243c088c674)


## RESULT:
The program for implementing simple webserver is executed successfully.
