# Understanding Regex: Matching a URL

## Introduction
In this tutorial, we'll break down a regular expression (regex) used to match URLs. Regular expressions allow developers to define specific search patterns to match, search, and validate strings. This regex is particularly useful for ensuring a valid URL structure.

## Summary
The regular expression `/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/` is used to match a valid URL, with or without protocols like `http` or `https`. The regex ensures that the input follows a standard URL format, including an optional protocol, domain name, top-level domain, and optional path.

## Table of Contents
- [Anchors](#anchors)
- [Protocol](#protocol)
- [Domain Name](#domain-name)
- [Top-Level Domain](#top-level-domain)
- [Path](#path)

## Regex Components

### Anchors
**Explanation**: Anchors `^` and `$` assert the start and end of the string. This ensures that the entire string matches the pattern, not just a part of it.

- **`^`**: Asserts the beginning of the string.
- **`$`**: Asserts the end of the string.

**Example**:
- `^https://example.com$` will match `https://example.com` but not `abc https://example.com def`.

### Protocol
**Explanation**: `(https?:\/\/)?` matches either `http://` or `https://`, and it's optional due to the `?` at the end. `s?` makes the "s" optional, allowing both "http" and "https".

- **`https?`**: Matches "http" or "https".
- **`\/\/`**: Escapes the forward slashes for URL format.
- **`?`**: Makes the protocol optional, allowing URLs without it.

**Example**:
- Matches: `https://example.com`, `http://example.com`, or `example.com`.

### Domain Name
**Explanation**: `([\da-z\.-]+)` matches the main part of the URL. It allows letters, numbers, dots (for subdomains), and hyphens.

- **`[a-z]`**: Matches lowercase letters.
- **`\d`**: Matches digits.
- **`\.`**: Matches a dot.
- **`-`**: Matches hyphens.
- **`+`**: Ensures that at least one character is present.

**Example**:
- Matches: `example.com`, `sub.example.com`, `example-123.com`.

### Top-Level Domain (TLD)
**Explanation**: `\.([a-z\.]{2,6})` ensures that the top-level domain has 2 to 6 characters, allowing for common TLDs like `.com`, `.org`, `.co.uk`.

- **`\.`**: Matches the dot before the TLD.
- **`[a-z\.]{2,6}`**: Matches 2 to 6 lowercase letters or dots (for multi-part TLDs like `.co.uk`).

**Example**:
- Matches: `.com`, `.org`, `.co.uk`, `.edu`.

### Path
**Explanation**: `([\/\w \.-]*)*\/?` matches the path, allowing slashes, letters, numbers, dots, hyphens, and underscores.

- **`\/`**: Matches a forward slash.
- **`\w`**: Matches any word character (letters, digits, underscores).
- **`\.`**: Matches a dot.
- **`-`**: Matches hyphens.
- **`*`**: Allows this part to be optional or repeated multiple times.
- **`\/?`**: Allows an optional trailing forward slash.

**Example**:
- Matches: `/about`, `/files/file1.txt`, `/docs/intro/`, or no path at all.

## Conclusion
This regular expression provides a comprehensive way to validate URLs. By allowing optional protocols, domains with multiple subdomains or hyphens, and flexible paths, it can handle most common URL formats used on the web today.

## Author
This tutorial was written by [Yeheyis](https://github.com/yeheyis1), a web development student passionate about learning regex and web technologies.
