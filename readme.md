A simple HTTP webserver. 
# HTTP-WebServer-Swift


## Documentation

```#if os(Linux)
import Glibc
#else
import Darwin.C
#endif
```
Importing a nessecary dependency when on Linux, else Darwin.C on MacOS

```let portNumber = UInt16(0000)```
Defines the given port for the webserver (Does NOT detect if port is in use to switch)

```print("Server listening on Localhost:\(portNumber)") ```
Sends a  message to the console notifying the developer the server  is ready, and lists the port (Localhost:0000 == 127.0.0.1:0000) 

```let client = accept(sock, nil, nil)
let html = "<!DOCTYPE html><html><body style='text-align:center;'><h1>Hello from <a href='https://swift.org'>Swift</a> Web Server.</h1></body></html>"
let httpResponse: String = """
  HTTP/1.1 200 OK
  server: simple-swift-server
  content-length: \(html.count)
  
  \(html)
  """
  ```
  Accepts the request from the user, then shows the HTML. (Warning, under \(html.count) and above \(html) a blank line is required)
