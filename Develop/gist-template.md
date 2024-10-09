# Understanding Regex: Matching a URL

##  Introduction
In this tutorial, we'll break down a regular expression (regex) used to match URLs. Regular expressions allow developers to define specific search patterns to match, search, validate strings. This regex is particularly useful for ensuring a vaild URL structure.

## Summary

The regular expression  `/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/` is used to match a valid URL, with or without protocols like `http` or `https`. The regex ensures that the input follows a standard URL format, including an optional protocol, domain name, top-level domain, and optional path.


## Table of Contents

- [Anchors](#anchors)
### Anchors
- [Protocol](#protocol) 
### Protocol

- [Domain Name](#domain-name)
### Domain Name

- [Top-Level Domain](#top-level-domain)
### Top-Level Domain (TLD)

- [Path](#path)
### Path

([\/\w \.-]*)*\/?:
- `\/`: Matches the forward slash.
- `\w`: Matches any word character (letters, digits, or underscores).
- `\.`: Matches the dot.
- `*`: Allows the path to be optional or repeated.
- `\/?`: Allows for an optional trailing forward slash.


## Conclusion
This regular expression provides a comprehensive way to validate URLs. By allowing optional protocols, domains with multiple subdomains or hyphens, and flexible paths, it can handle most common URL formats used on the web today.

## Author
This tutorial was written by [Yeheyis](https://github.com/yeheyis1), a web development student passionate about learning regex and web technologies.

