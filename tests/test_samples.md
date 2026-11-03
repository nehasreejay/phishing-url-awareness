# Test Results

Python version used: 3.13.9 | Operating system: Windows | Date: 29 Oct 2026

| # | Input | Expected result | Actual result | Pass/Fail |
|---|-------|-----------------|---------------|-----------|
| 1 | https://www.example.com/login | No listed warning signs | No listed warning signs found. This does NOT prove safety. | PASS |
| 2 | http://192.0.2.10/account | IP address + HTTP | Uses an IP address; Uses HTTP | PASS |
| 3 | http://example.com@sample.invalid/login | @ symbol + HTTP | Contains an @ symbol; Uses HTTP | PASS |
| 4 | https://a.b.c.d.e.example.invalid/path | Many hostname segments | Contains many hostname segments/subdomains | PASS |
| 5 | https://xn--example.invalid/ | Punycode-style hostname | Contains a punycode-style hostname | PASS |

## Notes
I learned that a URL can be checked just by reading its text, and that one URL can trigger more than one warning, like the IP address and HTTP checks in test 2. What surprised me was test 1: https://www.example.com/login showed no warnings, which taught me that "no warnings found" does not mean a link is safe. The tool only checks six clues and never opens the URL, so it can miss dangerous links.