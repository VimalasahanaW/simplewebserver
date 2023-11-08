# EX01 Developing a Simple Webserver
## Date:08-11-2023

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
<html>
<title>Top five Revenue Generating Software Companies</title>
<body>
<table border="2" cellspacing="10" cellpadding="6">
<caption>Top five Revenue Generating Software Companies</caption>
<tr>
<th>S.NO</th>
<th>Company</th>
<th>Revenue</th>
</tr>
<tr>
<td><center> 1 </center></td>
<td>Microsoft</td>
<td>65 Billion</td>
</tr>
<tr>
<td><center> 2 </center></td>
<td>Oracle</td>
<td>29.6 Billion</td>
</tr>
<tr>
<td><center> 3 </center>
<td>IBM</td>
<td>29.1 Billion</td>
</tr>
<tr>
<td><center> 4 </center>
<td>SAP</td>
<td>6.4 Billion</td>
</tr>
<tr>
<td><center> 5 </center>
<td>Symantec</td>
<td>5.6 Billion</td>
</tr>
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
![Alt text](<Screenshot 2023-11-08 180455.png>)
![Alt text](<Screenshot 2023-11-08 180525.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
