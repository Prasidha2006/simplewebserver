# EX01 Developing a Simple Webserver
## Date: 01/06/2025

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
'''
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """

<html>
    <body>
        <h1 style="color:red;text-align: center">DEVICE CONFIGURATION-24011485</h1>
        <ul align="center">
            <b>Device name:</b>	PRASIDHA A - 212224230204 <br>
            <b>Processor:</b>	13th Gen Intel(R) Core(TM) i5-1335U   1.30 GHz <br>
            <b>Installed RAM:</b>	16.0 GB (15.7 GB usable) <br>
            <b>Device ID:</b>	15EEA3B2-7EF5-4DEC-903D-577382C3C005   <br>
            <b>Product ID:</b>	00342-42709-07393-AAOEM   <br>
            <b>System type:</b>	64-bit operating system, x64-based processor  <br>
            <b>Pen and touch:</b>	No pen or touch input is available for this display    <br>
            

        </ul>
    </body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8008)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()

'''

## OUTPUT:

![alt text](<Screenshot 2025-06-01 163335.png>)

![alt text](<Screenshot 2025-06-01 163420.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
