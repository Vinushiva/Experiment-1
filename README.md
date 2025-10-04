# EX01 Developing a Simple Webserver
## Date: 20/8/2025

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
content = """
<!DOCTYPE html>
<html>
<head>
    <title>Top AI & Generative AI Companies</title>
</head>
<body>
    <table border="2" cellspacing="10" cellpadding="6">
        <caption>Top 5 AI & Generative AI Companies by Impact</caption>
        <tr>
            <th>S.No</th>
            <th>Company / Platform</th>
            <th>Focus Area</th>
        </tr>
        <tr>
            <td>1</td>
            <td>OpenAI</td>
            <td>Generative AI, Language Models (ChatGPT)</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Google DeepMind</td>
            <td>AI Research, Generative AI, AlphaFold</td>
        </tr>
        <tr>
            <td>3</td>
            <td>Anthropic</td>
            <td>Safe and Responsible AI, LLMs</td>
        </tr>
        <tr>
            <td>4</td>
            <td>Microsoft AI</td>
            <td>AI Tools, Azure OpenAI Service</td>
        </tr>
        <tr>
            <td>5</td>
            <td>Stability AI</td>
            <td>Generative AI, Image Generation (Stable Diffusion)</td>
        </tr>
    </table>
</body>
</html>

"""

class myhandler (BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address, myhandler)
print("my webserv webserver is running...")
httpd.serve_forever()
```


## OUTPUT:
![alt text](<Screenshot 2025-10-03 152745.png>)
![alt text](<Screenshot 2025-10-03 152823.png>)


## RESULT:
The program for implementing simple webserver is executed successfully.

