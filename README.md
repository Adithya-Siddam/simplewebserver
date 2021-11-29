# Developing a Simple Webserver
## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation
### Step 2:
Design of webserver workflow
### Step 3:
Implementation using Python code
### Step 4:
Serving the HTML pages.
### Step 5:
Testing the webserver

## PROGRAM:
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1>Top 5 Programming languages</h1>
<h2>1. Javascript.</h2>
<h3>JavaScript (often shortened to JS) is a lightweight, interpreted, objectoriented language with first-class functions, and is best known as the scripting language for Web pages.</h3>
<br>
<h2>2. Python.</h2>
<h3>Python is an interpreted, object-oriented, high-level programming languagewith dynamic semantics. Its high-level built in data structures, combined withdynamic typing and dynamic binding, make it very attractive for Rapid Application Development.</h3>
<br>
<h2>3. C programming language.</h2>
<h3>C is a general-purpose programming language that is extremely popular, simple, and flexible to use. It is a structured programming language that is machine-independent and extensively used to write various applications,
Operating Systems like Windows, and many other complex programs like Oracle database, Git, Python interpreter, etc.</h3>
<br>
<h2>4. JAVA.</h2>
<h3>Java is a programming language and computing platform first released by Sun Microsystems in 1995. It has evolved from humble beginnings to power a large share of today’s digital world, by providing the reliable platform upon
which many services and applications are built.</h3>
<br>
<h2>5. R language.</h2>
<h3>R is a programming language and free software environment for statistical computing and graphics. It is supported by the R Core Team and the R Foundation for Statistical Computing.</h3>
<br>
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
server_address = ('',8080)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()

## OUTPUT:
## Client side output:
![client side](/IMAGES/img1.png)

![client side](/IMAGES/img2.png)
## Server side output:
![server side](/IMAGES/img3.png)

![server side](/IMAGES/img4.png)

![server side](/IMAGES/img5.png)
## RESULT:
Thus the simple webserver to serve HTML pages is created sucessfully.