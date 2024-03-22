# EX01 Developing a Simple Webserver
## Date:14-4-24

## AIM:
To develop a simple webserver to serve html pages.

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
from http.server import HTTPServer,BaseHTTPRequestHandler
```
content='''
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
<h1>Top Five Revenue from Companies</h1>
<table border=2>
<tr>
<th> Company Name</th>
<th> Revenue</th>
<th> Financial Year</th>
</tr>

<tr>
<td>TCS</td>
<td> $86.6</td>
<td> 2014</td>
</tr>
<tr>
<td>HCL</td>
<td> $31.51</td>
<td> 2017</td>
</tr>
<tr>
<td> HP</td>
<td> $345</td>
<td> 2018</td>
</tr>
<tr>
<td> RIL</td>
<td> $295</td>
<td> 2019</td>
</tr>
<tr>
<td>OYO</td>
<td> $135</td>
<td> 2019</td>
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
```
## OUTPUT:
![2024-03-14](https://github.com/gokulprakash23013924/simplewebserver/assets/150231472/8a20bfda-cc81-4b7a-872a-604395bf7428)

![926fabad-138a-4cce-a1c0-4e433c9bceed](https://github.com/gokulprakash23013924/simplewebserver/assets/150231472/c23bb013-0737-4ed0-b633-7902f997ed0a)



## RESULT:
The program for implementing simple webserver is executed successfully.
