# EX01 Developing a Simple Webserver
## Date:

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
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1>Top 5 Revenue Generating Companies<h1>
<UL TYPE=“circle”>
<LI> Walmart </LI>		
<LI> Saudi Aramco </LI>
<LI> State Grid Corporation of China </LI>
<LI> Amazon.com, Inc </LI>
<LI> Vitol </LI>
</UL>
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
```

## OUTPUT:

![image](https://github.com/ritiksamuel/simplewebserver/assets/130056055/a20659bb-f078-44cb-b408-eb1af8992164)
![image](https://github.com/ritiksamuel/simplewebserver/assets/130056055/5d35b036-c809-4f8d-909c-21cbd432ad79)


## RESULT:
The program for implementing simple webserver is executed successfully.
