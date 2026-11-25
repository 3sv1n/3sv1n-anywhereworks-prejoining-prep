# 3sv1n-anywhereworks-prejoining-prep
> Repository for tracking my anywhereworks pre-joining roadmap

## what's in this? 
1. A readme that tracks weekly updates, and theoretical questions
2. two mini-projects;
<br>
    a. a html form page to understand accessibility structures 
    <br>
    b. a single-page react app to understand setmore's booking UI 
3. conclusion of the mini-projects and roadmap



# Week 1 : Understanding the internet

## Lifecycle of a website from URL to webpage

### Every website you see on a screen can be explained as the final product of a process of 4 steps:
1. URL 
2. DNS Lookup
3. HTTP Request and Response 
4. Rendering

Let's understand the fundamentals of the website, and look up videos of cats doing somersaults.

#### 1. URL
First, lets get the url of the website we want to visit.

A URL (Uniform Resource Locator) is a unique string that identifies and locates a resource on the internet.

Every website has a unique URL which is typed into a browser. Example of a URL filled with fun videos of cats;

https://www.youtube.com

a typical URL consists mainly of 2 parts: the protocol and the domain. 

protocol: HTTP/S (HyperText Transfer Protocol/HyperText Transfer Protocol Secure)
domain: youtube.com


#### 2. DNS Lookup
Now that we have a URL, we can't just make a request to it. We need to find the IP address of the domain name. Think of an IP address as a phone number of a website, or in this case, the server where the website lives (or hosted).

A browser gets the ip address of a website from 2 sources
1. DNS cache
2. DNS servers (which consists of ISP DNS servers and root DNS servers)

The DNS cache consists of 3 different types:
1. Browser DNS cache
2. OS DNS cache
3. Router DNS cache

The DNS Servers consists of 2 different types:
1. ISP DNS servers
2. Root DNS servers

When a browser fails to recognize the IP address in any of these caches (due to the cats being very rare), it proceeds to look up the IP address from DNS servers.

The DNS servers works in a way that the server of the domain, for example .com, .org, etc, which is managed by Root DNS servers, returns the IP address of the authoritative name servers (the servers which contains DNS info) of the domain name. The authoritative name servers of the domain name returns the IP address of the web hosting server. 


#### 3. HTTP Request and Response
We have succesfully acquired the IP address of the server where the cats live, it's time to make a request to that server to get the contents of the webpage we want to visit.

Before we can make a request, there's a critical step in the modern internet, called the TCP handshake. 

The TCP handshake is a 3 step process that happens between the browser and the server. It is used to establish a secure, reliable connection between the browser and the server. 

##### Request
Request refers to the action of the browser asking the server for the contents of the webpage we want to visit. A request consists of 3 parts;
1. Request line: the method which we're doing (eg, GET, POST etc)
2. Header: key-value pairs that pass metadata to the server, such as information about the browser, region etc
3. an optional body (eg, data being sent in a login form)

A request generally looks like this

```bash
GET /search?q=cats+somersaults HTTP/1.1
Host: youtube.com
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.3
```

##### Response
Response refers to the action of the server sending the contents of the webpage to the browser. A response consists of 3 parts;
1. Status line: the status code and status message (eg, 200 OK, 404 Not Found etc)
2. Header: key-value pairs that pass metadata to the browser, such as information about the server, content type etc
3. an optional body (eg, the HTML, CSS, and JavaScript code of the webpage)

A response generally looks like this

```bash
HTTP/1.1 200 OK
Content-Type: text/html
Content-Length: 12345
```

In this case, the website server returns to us a html file, a CSS styling and JavaScript code.

These files are then downloaded and assembled in the browser, in a step called

> HTML – HyperText Markup Language
<br>
> CSS – Cascading Style Sheets

##### 4. Rendering
Rendering is the process of the browser assembling the HTML, CSS, and JavaScript code into a webpage.

The HTML source is first constructed into a parent-child item tree called the DOM (Document Object Model). right after the browser builds the DOM (from HTML) and CSSOM (from CSS), it merges them into the Render Tree, calculates element sizes and positions (Layout / Reflow), and then draws the Pixels onto the screen (Paint)

eg; 

```html
<body>
    <p>I'm some text</p>
    <a href="#">Link</a>
</body>
```
whic is constructed as;

```ascii
Body
├─ P    
|   └─ "I'm some text"
└─ A
    └─ "Link"
```


but the website looks pretty boring. So let's add some styling with the CSS that's given to us. 

Think of a CSS like a ruleset which instructs the browser the exact styling that each element needs to be applied with, specified using 'selectors'

eg;

```css
body {
    background-color: blue;
}
```

> A selector can be defined in 3 ways. either an element name, a ID (# selector), or a class (. selector)

Once the browser has loaded the css file, it applies the styling to the DOM. Since we only have rules for one element, it becomes pretty straightforward; 

find the body element -> change the background color to blue

If CSS has many element selectors, they are processed according to the rules and styles are applied. 


And that's it! The end product is a styled webpage that we can interact with. 