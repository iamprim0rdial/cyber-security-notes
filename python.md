## Variable and Data Type:
```bash
port = 8080 # int
url = "http://github.com" # string
version = 5.5 # float
vulnerable = True # boolean, True or False
domains ['github.com', 'medium.com', 'hackerone.com', 'gitbook.com'] # list
ip("192.168.1.11", "192.168.1.10") # tuple
server = {
            "verily": "nginx",
             "flipkart": "envoy"
         } # dictionary
vulnerable_versions = (4.4,4.5, 4.6,4.7} # set
'''
This is the multi line comments,
which is used to describe the code.
This part is ignored at runtime.
'''
```
---
## Strings
```bash

url = "https://www.github.com"
print(url[7])  # 'w' is in 8th position. Index starts from 'h' at position 0.
print(len(url))  # prints the number of characters in the URL
print(url.upper())  # Converts all characters in the URL to uppercase
print(url.lower())  # Converts all characters in the URL to lowercase
print("github" in url)  # Returns True if 'github' is found in the URL

new_url = url.replace("github", "gitlab")  # Replaces 'github' with 'gitlab'
print(new_url)  # prints 'https://www.gitlab.com'
print(url[8:14])  # Extracts 'github' from the URL (from index 8 to 14)
print(url.split("."))  # splits the URL at every '.' and returns a list
print(url.find("github"))  # Returns the index of the first occurrence of 'github'
print(url.startswith("https"))  # Returns True since the URL starts with 'https'
print(url.endswith(".com"))  # Returns True since the URL ends with '.com'

```
---

## Try and Catch 
- try and catch are use to handle the exception 
- try block contains code that can raise an exception and except block contain code to handle that exception

Note: exception: An exception is an error that occurs during the execution of a program, which disrupts its normal flow.

---

## Python Library for bug hunting

1. **Scapy :** Scapy is a powerful Python library used for network packet manipulation. It allows users to create, send, receive, and analyze network packets.
2. **Nmap (python-nmap):** Nmap is a popular network scanning tool, and python-nmap is a Python library that provides a way to interact with Nmap
3. **pycryptodump:**  A self-contained Python library for cryptographic operations, serving as a modern replacement for PyCrypto.
4. **Paramiko:** Paramiko is a Python library that provides tools for SSH (Secure Shell) connectivity.
5. **Requests:** Requests is a simple yet powerful Python library for making HTTP requests.
6. **Pwntool:** Pwntools is a CTF framework and exploit development library.
7. **Argprase:**  The argparse library is an incredibly useful tool that significantly simplifies the process of creating command-line interfaces by effectively parsing command-line arguments and options provided by users.
8. **DNSpython:**  dnspython is a DNS toolkit for Python that supports various record types and can perform queries, zone transfers, and dynamic updates, including TSIG-authenticated messages and EDNS0.
9. **Subprocess:** The Subprocess module provides a powerful mechanism that allows you to spawn new operating system processes, connect to their input/output/error pipes, and obtain their return codes for further processing and analysis.
10. **Socket:**  A Socket is a useful library for communication between computers. Very important especially in the aspect of malware, especially for CnC servers, which control hacked devices by providing IP addresses and ports for sending data.
11. **ctypes:**  The ctypes library in Python lets you use C libraries or system shared libraries (DLLs on Windows, .so files on Linux). With ctypes, you can call C functions, manage memory directly, and work with low-level system APIs. 
12. **Impacket:** Impacket is a collection of Python3 classes focused on providing access to network packets. Impacket allows Python3 developers to craft and decode network packets in simple and consistent manner.
13. **BeautifulSoup:** BeautifulSoup is a powerful library in Python used for web scraping purposes.

- Installations
    - Scapy: `pip install scapy`
    - python-nmap: `pip install python-nmap`
    - pycryptodome: `pip install pycryptodome`
    - Paramiko: `pip install paramiko`
    - Requests: `pip install requests`
    - Pwntools: `pip install pwntools`
    - DNSpython: `pip install dnspython`
    - Impacket : `python3 -m pipx install impacket`
    - BeautifulSoup : `pip install beautifulsoup4`
