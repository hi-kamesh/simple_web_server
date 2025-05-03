# EX01 Developing a Simple Webserver

# Date:
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

    from http.server import HTTPServer,BaseHTTPRequestHandler

    content='''
    <!doctype html>
    <html>
    <head>
    <title>Laptop Configuration</title>
    </head>
    <body align="center"><h1>LAPTOP CONFIGURATION</h1>
    <table border="5" align="center">
    <tr>
        <th bgcolor="grey">
            LAPTOP CONFIGURATION
        </th>
        <th bgcolor="grey">
            DESCRIPTION
        </th>
    <tr>
        <td>
            Device Name
        </td>
        <td>
            DESKTOP-MOHHBTU 
        </td>
    </tr>
    <tr>
        <td>
            Processor
        </td>
        <td>
            12th Gen Intel(R) Core(TM) i5-1235U   1.30 GHz
        </td>
    <tr>
        <td>
            Installed RAM
        </td>
        <td>
            16.0 GB (15.7 GB usable)
        </td>
    </tr>
    <tr>
        <td>
            Device ID
        </td>
        <td>
            15EEA3B2-7EF5-4DEC-903D-577382C3C005
        </td>
    </tr>
    <tr>
        <td>
            Product ID
        </td>
        <td>
            00342-42648-28891-AAOEM
        </td>
    </tr>
    <tr>
        <td>
            System Type
        </td>
        <td>64-bit operating system, x64-based processor</td>
    </tr>
    </table>
    </body>
    </html>
    '''

    class MyServer(BaseHTTPRequestHandler):
        def do_GET(self):
            print("Get request received...")
            self.send_response(200) 
            self.send_header("content-type", "text/html")       
            self.end_headers()
            self.wfile.write(content.encode())

    print("This is my webserver") 
    server_address =('',8000)
    httpd = HTTPServer(server_address,MyServer)
    httpd.serve_forever()

# OUTPUT:
![image](https://github.com/user-attachments/assets/5157c6ca-ff00-40e5-b872-92e9cb8e2a6b)
![image](https://github.com/user-attachments/assets/1869cca1-70f5-4766-9bf9-b9b647e8ccd7)

# RESULT:
The program for implementing simple webserver is executed successfully.
