# EX01 Developing a Simple Webserver

# Date:24-10-2024
# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
    <body>
        <h1 align="center">Laptop Configuration(YUVASHREE 24900809)</h1>
        <ol type="1">
            <li><b>Device name</b> yuvas
            <li><b>Processor</b>12th Gen Intel(R) Core(TM) i5-1235U 1.30 GHz
            <li><b>Installed RAM</b>16.0 GB (15.7 GB usable)
            <li><b>Device ID<b>5E11FFB9-7C97-42E2-A2F8-34FD2037892D
            <li><b>Product ID<b>00342-42708-50104-AAOEM
            <li><b>System type</b> 64-bit operating system, x64-based processor
            <li><b>Pen and touch</b> No pen or touch input is available for this display
        </ol>
    </body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type','text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```
# OUTPUT:
![alt text](<Screenshot (17).png>)
![alt text](<Screenshot (18).png>)
![Screenshot (30)](https://github.com/user-attachments/assets/4bc6f38e-adfc-4407-b39b-a597d497404b)


# RESULT:
The program for implementing simple webserver is executed successfully.
