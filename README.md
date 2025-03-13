# EX01 Developing a Simple Webserver
## Date: 09/03/2025

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
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TCP and IP Protocols List</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 20px;
            padding: 20px;
        }
        .container {
            max-width: 600px;
            background: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        h2 {
            color: #333;
            text-align: center;
        }
        h3 {
            color: #555;
            border-bottom: 2px solid #ddd;
            padding-bottom: 5px;
        }
        ul {
            list-style-type: none;
            padding: 0;
        }
        li {
            padding: 8px 0;
            font-size: 16px;
            color: #444;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>List of TCP and IP Protocols</h2>
        <h3>TCP Protocols</h3>
        <ul>
            <li>FTP (File Transfer Protocol)</li>
            <li>HTTP (Hypertext Transfer Protocol)</li>
            <li>HTTPS (Hypertext Transfer Protocol Secure)</li>
            <li>SMTP (Simple Mail Transfer Protocol)</li>
            <li>POP3 (Post Office Protocol 3)</li>
            <li>IMAP (Internet Message Access Protocol)</li>
            <li>SSH (Secure Shell)</li>
            <li>Telnet</li>
        </ul>
        <h3>IP Protocols</h3>
        <ul>
            <li>ICMP (Internet Control Message Protocol)</li>
            <li>IGMP (Internet Group Management Protocol)</li>
            <li>UDP (User Datagram Protocol)</li>
            <li>ESP (Encapsulating Security Payload)</li>
            <li>AH (Authentication Header)</li>
            <li>OSPF (Open Shortest Path First)</li>
            <li>BGP (Border Gateway Protocol)</li>
        </ul>
    </div>
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
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()

## OUTPUT:
!![alt text](<Screenshot (67).png>)
![Screenshot (68)](https://github.com/user-attachments/assets/053459d6-ba2c-4c1c-ad15-e5f2f1452007)


## RESULT:
The program for implementing simple webserver is executed successfully.
