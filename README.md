# EX01 Developing a Simple Webserver

# Date:19/09/2025
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
from http.server import HTTPServer,BaseHTTPRequestHandler
content='''<!DOCTYPE html>
<html lang ="en">
<head>
              <meta charset="UTF-8">
              <meta name="viewport content="width=device-width,initiaL-scale=1.0">
              <title>LAPTOP SPECIFICATION></title>
  
</head>
<body bgcolor="FF99CC">

<b><h1 align="center"><font color="990066">***LAPTOP SPECIFICATION***</font></h1></b>
<h1 align="center"><font color="green">~DEVICE SPECIFICATION~</font></h1>
<ul Type='none'align="center">
<h2><li><font color="AA0000">Device Namer:</font><font color="0000AA">Laptop-RST66PH2</font></h2></li>
<h2><li><font color="AA0000">Processor:</font><font color="0000AA">AMD Ryzen 58645HS W/Radeon 760M Graphics (4.30 Ghz)</font></h2></li>
<h2><li><font color="AA0000">Installed RAM:</font><font color="0000AA">16.0 GB(15.3 GB usable)</font></h2></li>
<h2><li><font color="AA0000">Device ID:</font><font color="0000AA">O7956842-6396-47D9-923F-819B42CD7C2D</font></h2></li>
<h2><li><font color="AA0000">Product ID:</font><font color="0000AA">00342-42736-28633-AAOEM</font></h2></li>
<h2><li><font color="AA0000">System type:</font><font color="0000AA">64-bit operating system,x64-based processor</font></h2></li>
<h2><li><font color="AA0000">Pen and Touch:</font><font color="0000AA">No pen or touch input is available for this display</font></h2></li>
</ul>
<h1 align="center"><font color="green">~Windows Specification~</font></h1>
<ul Type='none' align="center">
<h2><li><font color="AA0000">Edition:</font><font color="0000AA">Windows 11 Home Single Language</font></h2></li>
<h2><li><font color="AA0000">Version:</font><font color="0000AA">24Hz</font></h2></li>
<h2><li><font color="AA0000">Installed on:</font><font color="0000AA">31-08-2025</font></h2></li>
<h2><li><font color="AA0000">OS build:</font><font color="0000AA">26100.4946</font></h2></li>
<h2><li><font color="AA0000">Experience:</font><font color="0000AA">Windows Feature Experience Pack 1000.26100.197.0</font></h2></li>
</ul>
</body>
</html>'''
class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200)
        self.send_header("content-type", "text/html")
        self.end_headers()
        self.wfile.write(content.encode())
print("This is my webserver")
server_address=('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()        
```
# OUTPUT
![alt text](<Screenshot 2025-09-19 072627.png>)
![alt text](<Screenshot 2025-09-19 173542.png>)

# RESULT:
The program for implementing simple webserver is executed successfully.
