# EX01 Developing a Simple Webserver
## Date: 29/8/25

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
```
from http.server import HTTPServer, BaseHTTPRequestHandler 
content="""
<HTML>
    <HEAD>
        <TITLE>
           Web server
        </TITLE>
    </HEAD>
    <BODY>
        <table border ='1' align="CENTER" cellpadding ="10" bgcolor="WHITE">
        <caption>
            <h1>
                List of Protocols in TCP/IP Protocol Suite
            </h1>
        </caption>
        <tr>
            <th>
                S.NO
            </th>
            <th>
                Name of the Layer
            </th>
            <th>
                Name of the Protocol layer
            </th>
        </tr>
        <tr>
            <td>
                1.
            </td>
            <td>
                Application Layer 
            </td>
            
            <td>
                HTTP, FTP, DNS, Telnet
            </td>
        </tr>
        <tr>
            <td>
                2.
            </td>
            <td>
                Transport Layer
            </td>
            
            <td>
                TCP & UDP
            </td>
        </tr>
        <tr>
            <td>
                3.
            </td>
            <td>
                Network Layer
            </td>
            
            <td>
                IPV4/IPV6
            </td>
        </tr>
        <tr>
            <td>
                4.
            </td>
            <td>
                Data Link Layer
            </td>
            <td>
                Ethernet
            </td>

        </tr>


    </BODY>
</HTML>
"""
class myhandler (BaseHTTPRequestHandler):
     def do_GET(self):
        print("request received") 
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('', 5000)
httpd = HTTPServer(server_address,myhandler)
print("My webserver is running")
httpd.serve_forever()
```

## OUTPUT:
<img width="1215" height="290" alt="Screenshot 2025-08-29 091817" src="https://github.com/user-attachments/assets/f0a9e637-939e-4f63-8bc6-76c1a08d0e74" />
<img width="1730" height="749" alt="Screenshot 2025-08-29 091848" src="https://github.com/user-attachments/assets/60102b8f-b416-4865-828a-318cf704a0b2" />


## RESULT:
The program for implementing simple webserver is executed successfully.
