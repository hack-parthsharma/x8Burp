<h3 align="center">Hidden parameters discovery suite wrapper</h3>

<p align="center"><img src="https://user-images.githubusercontent.com/87244850/126019752-09dc8b3c-c6a4-49f3-9398-7974cbae3d03.png" width="50%"/></p>

The tool helps to find hidden parameters that can be vulnerable or can reveal interesting functionality that other hunters miss. Greater accuracy is achieved thanks to the line-by-line comparison of pages, comparison of response code and reflections.

## Features

- Selecting multiple requests from the Proxy or Repeater tab.
- Each selected request is executed in a separate thread.
- Automatic Issue creation when hidden parameter is found.
- HTTP/2 Support.
- Requests with detected parameters are visible in the Proxy tab.
- Issue is added with severity `Information` when WAF is detected.
- Automatic detection of injection point. If the request body exists, then parameters in URL-Query are ignored.
- Custom injection point can be defined using `%s` or `&%s`
<p align="center"><img src="https://user-images.githubusercontent.com/87244850/125835832-a24d2cec-4dc1-4ffd-afff-12f4e99c409c.png" width="79%"/></p>

## Usage
- There are four search choices available: 
    - Small Wordlist (Recommended, `25000` words, 5 threads)
    - Large Wordlist (`63000` words, 15 threads)
    - x8083 - all request will be proxied via port 8083 (for example, you can configure the port in Burp)
    - Debug Params - the minimum number of requests to detect only debug parameters and parameters based on response

<p align="center">&#160;&#160;&#160;&#160;&#160;&#160;<img src="https://user-images.githubusercontent.com/87244850/125835974-5679ec1a-0126-48a2-82ba-1861c94ed551.png" width="83%"/></p>


## Test
Feel free to check whether the tool works as expected and compare it with other tools at https://4rt.one/index.html There are 2 reflected parameters, 4 parameters that change code/headers/body, and one extra parameter with a not random value.

## To Do
- [ ] Implementation of a panel for configuring custom proxy
- [x] Windows version
- [ ] Implementation of a choice - `25000` words, 1 thread
- [ ] Publish to BApp Store


## Installation
You need to configure [Jython Standalone](https://www.jython.org/download.html) path in Burp Suite Extender options. <br>
As this is a wrapper, a [precompiled binary](https://github.com/Sh1Yo/x8/releases/tag/v2.5.0) is used.
- Linux
    - from releases
        ```bash
        Burp -> Extender -> ./x8-Burp/linux_x8.py
        ```
- Windows
    - from releases
        ```bash
        Burp -> Extender -> ./x8-Burp/win_x8.py
        ```
