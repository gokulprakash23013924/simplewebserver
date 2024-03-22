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
<td> Micro Soft</td>
<td> $86.6</td>
<td> 2014</td>
</tr>
<tr>
<td> tesla</td>
<td> $31.51</td>
<td> 2017</td>
</tr>
<tr>
<td> apple inc</td>
<td> $345</td>
<td> 2018</td>
</tr>
<tr>
<td> tata</td>
<td> $295</td>
<td> 2019</td>
</tr>
<tr>
<td> walmart</td>
<td> $135</td>
<td> 2019</td>
</tr>
<tr>
<td> Amazon.com Inc.</td>
<td> $386.6</td>
<td> 2014</td>
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

![Screenshot 2024-03-14 140942](https://github.com/gokulprakash23013924/simplewebserver/assets/150231472/dedd898c-e20f-4684-bab2-3bf9046ad37d)


## RESULT:
The program for implementing simple webserver is executed successfully.
