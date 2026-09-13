
# 🐧 Day 8 — Linux Web & Command-Line Tools

Today is **Day 8 of my Linux learning journey**.

Today I learned about two cool web-related things:

1. How to start a local web server using the command line.
2. How to communicate with websites/web servers using command-line tools such as `curl` and `wget`.

## 🌐 1. Start a Web Server Using Python

Python can create a simple local web server directly from the terminal.

```bash
python -m http.server 8080
```

This starts a web server on:

```text
http://localhost:8080
```

The server shares files from the directory where the command was executed.

You can open the address in a web browser and see the files available in that directory.

The port can be changed by replacing `8080` with another port:

```bash
python -m http.server 7600
```

Now the server will be available at:

```text
http://localhost:7600
```

## 🐘 2. Start a Web Server Using PHP

PHP also has a built-in development server.

```bash
php -S 127.0.0.1:8085
```

This starts a local PHP web server on port `8085`.

You can access it using:

```text
http://127.0.0.1:8085
```

`127.0.0.1` is the loopback address, which refers to the local machine.

## 🔌 3. Changing the Apache Port

Apache's listening ports can be configured in:

```bash
sudo nano /etc/apache2/ports.conf
```

Inside the file, you may see a line such as:

```text
Listen 80
```

To change the Apache listening port, change the `Listen` line.

For example:

```text
Listen 8080
```

After changing Apache's configuration, the service needs to be restarted for the change to take effect.

```bash
sudo systemctl restart apache2
```

> ⚠️ Be careful when changing Apache ports because other Apache configuration files, such as virtual host configurations, may also reference the old port.

## 🧑‍💻 4. Talk to a Web Server from the Command Line with `curl`

`curl` is a command-line tool used to transfer data to and from URLs.

`curl` stands for **Client URL**.

For example:

```bash
curl localhost:7600
```

This sends a request to the local web server running on port `7600`.

If the server returns an HTML page, `curl` displays the HTML directly in the terminal.

You can also write the response to a file:

```bash
curl -o Coolwebsite localhost:8080
```

Here:

```text
-o → output the response to a file
Coolwebsite → name of the output file
localhost:8080 → URL being requested
```

The downloaded HTML response is saved inside the file named:

```text
Coolwebsite
```

You can view the contents using:

```bash
cat Coolwebsite
```

`cat` displays the contents of a file in the terminal.

## 📋 5. View HTTP Response Headers with `curl -I`

The following command displays the HTTP response headers:

```bash
curl -I localhost:8080
```

Example:

```text
HTTP/1.0 200 OK
Content-type: text/html
```

### What does `200 OK` mean?

`200 OK` means the HTTP request was successful.

Some common HTTP status codes are:

```text
200 → OK / Successful request
301 → Moved Permanently
302 → Found / Temporary redirect
400 → Bad Request
401 → Unauthorized
403 → Forbidden
404 → Not Found
500 → Internal Server Error
```

`404 Not Found` means the requested resource could not be found on the server.

## 🔎 6. Verbose Mode with `curl -v`

The `-v` option enables verbose output.

```bash
curl -v localhost:8080
```

This shows additional information about the request and response, such as:

* Connection details
* Request headers
* Response headers
* HTTP status
* Data transferred

This is useful when troubleshooting web-server or HTTP problems.

## 📥 7. Download Web Content Using `wget`

`wget` is another command-line tool that can download files and web content.

For example:

```bash
wget localhost:7600
```

If the server provides an `index.html` page, `wget` can download the page.

The downloaded file may be saved as:

```text
index.html
```

You can then inspect it using:

```bash
cat index.html
```

## 🧠 Important Commands Learned

| Command                              | Purpose                                         |
| ------------------------------------ | ----------------------------------------------- |
| `python -m http.server 8080`         | Start a simple Python web server                |
| `php -S 127.0.0.1:8085`              | Start a PHP development web server              |
| `sudo nano /etc/apache2/ports.conf`  | Edit Apache port configuration                  |
| `sudo systemctl restart apache2`     | Restart Apache                                  |
| `curl localhost:7600`                | Request a web page from the command line        |
| `curl -o Coolwebsite localhost:8080` | Save the response to a file                     |
| `cat Coolwebsite`                    | Display the downloaded file                     |
| `curl -I localhost:8080`             | Display HTTP response headers                   |
| `curl -v localhost:8080`             | Show detailed HTTP request/response information |
| `wget localhost:7600`                | Download content from a web server              |

## ⭐ Key Things I Learned

```text
Python HTTP Server
    ↓
python -m http.server 8080

PHP HTTP Server
    ↓
php -S 127.0.0.1:8085

Change Apache Port
    ↓
sudo nano /etc/apache2/ports.conf

Request a Website
    ↓
curl localhost:7600

Save Website Response
    ↓
curl -o Coolwebsite localhost:8080

Read Saved File
    ↓
cat Coolwebsite

View Response Headers
    ↓
curl -I localhost:8080

Detailed HTTP Information
    ↓
curl -v localhost:8080

Download Web Content
    ↓
wget localhost:7600
```

## 🎓 Day 8 Summary

Today I learned how to interact with web servers directly from the Linux command line.

I learned how to create a simple local web server using **Python and PHP**, how to change an **Apache listening port**, and how to communicate with web servers using **`curl` and `wget`**.

I also learned about **HTTP response headers**, HTTP status codes such as **`200 OK` and `404 Not Found`**, downloading web content, and using `curl -v` to troubleshoot HTTP connections.

This helped me understand that a web browser is not the only way to communicate with a website — Linux command-line tools can also interact directly with web servers.
