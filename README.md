# EX01 Developing a Simple Webserver
## Date:29/02/2024

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
<table border ="4" cellspacing="6" cellpadding="6">
<caption>Top Ten Companies by Revenue</caption>
    <tr>
        <th>Rank</th>
        <th>Company</th>
        <th>Revenue</th>
        <th>FY</th>
        <th>Market cap</th>
        <th>Headquaters</th>
    </tr>
    <tr>
        <td>1</td>
        <td>Microsoft</td>
        <td>$86.8</td>
        <td>2014</td>
        <td>$370.3</td>
        <td>Washington</td>
    </tr>
    <tr>
        <td>2</td>
        <td>Oracle</td>
        <td>$37.1</td>
        <td>2013</td>
        <td>$79.4</td>
        <td>CA</td>    
    </tr>
    <tr>
        <td>3</td>
        <td>SAP</td>
        <td>$20.9</td>
        <td>2013</td>
        <td>$35.5</td>  
        <td>Germany</td>
    </tr>
    <tr>
        <td>4</td>
        <td>Symantec</td>
        <td>$6.8</td>
        <td>2013</td>
        <td>$14</td>
        <td>CA</td>  
    </tr>
    <tr>
        <td>5</td>
        <td>VMware</td>
        <td>$5.2</td>
        <td>2013</td>
        <td>$41.03</td>
        <td>CA</td>
    </tr>
    <tr>
        <td>6</td>
        <td>CA Technologies</td>
        <td>$4.7</td>
        <td>2013</td>
        <td>$11.6</td>
        <td>New York</td>
    </tr>
    <tr>
        <td>7</td>
        <td>Adobe Systems</td>
        <td>$4.4</td>
        <td>2013</td>
        <td>$10.2</td>
        <td>CA</td>
    </tr>
    <tr>
        <td>8</td>
        <td>Fiserv</td>
        <td>$4.5</td>
        <td>2013</td>
        <td>$6.5</td>
        <td>Brookefield</td>
    </tr>
    <tr>
        <td>9</td>
        <td>Intuit</td>
        <td>$4.2</td>
        <td>2013</td>
        <td>$5.1</td>
        <td>CA</td>
    </tr>
    <tr>
        <td>10</td>
        <td>Amadeus IT Group</td>
        <td>$3.8</td>
        <td>2013</td>
        <td>$5.1</td>
        <td>Madrid</td>
    </tr>     
</table>
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
![alt text](<Screenshot 2024-03-15 091916.png>)
![alt text](<Screenshot 2024-03-15 092442.png>)


## RESULT:
The program for implementing simple webserver is executed successfully.
