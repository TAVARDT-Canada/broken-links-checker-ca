# Broken Link Checker and Dead Link Detector

[![Broken Link Checker](https://img.shields.io/badge/TAVARDT-Broken%20Links-5b3cf5.svg)](https://tools.tavardt.com/ca/broken-link-checker/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)

Audits internal and external hyperlinks, detecting HTTP 404 errors, dead links, and crawl budget leaks.

***

## Risk Vectors and Operational Impact in Hyperlink Architecture

Broken links returning 404 errors impair user trust and waste valuable search crawler capacity across Canadian digital platforms. When search robots encounter broken paths, crawl schedules are truncated, leading to delayed indexation.

Unresolved external links erode topical authority and compromise AI citation engines during algorithmic reviews. Automated link verification maintains internal navigation integrity and guarantees dependable user journeys.

***

## Core Technical Audit Capabilities

* **Comprehensive Anchor Tag Extraction**: Parses and normalises all anchor href attributes while filtering out local hash fragments, telephone links, and mailto schemas.
* **Internal and External Link Segregation**: Automatically classifies discovered URLs based on the root domain to separate internal architecture from outbound citations.
* **Bandwidth-Optimized HEAD Probing**: Evaluates destination status codes via lightweight HTTP HEAD requests without downloading complete payload bodies.
* **Automated GET Fallback Mechanism**: Retries connections using standard GET requests when remote servers reject HEAD methods with 403 or 405 status codes.
* **Dead Link and Error Code Detection**: Flags HTTP 4xx client errors, 5xx server failures, and network timeouts with granular diagnostic output.
* **Link Quality Health Score**: Computes an objective 0 to 100 quality metric categorising health into SATISFACTORY, ADVISORY, or UNSATISFACTORY.
* **Structured JSON Export**: Emits machine-readable audit data via short CLI flags for seamless continuous integration deployment.

***

## Installation and Execution

Requires Python 3.8 or higher utilizing only Python standard libraries.

```bash
git clone https://github.com/TAVARDT-Canada/broken-links-checker-ca.git
cd broken-links-checker-ca
python broken_links_scanner.py https://company.ca
```

To output structured JSON for automated pipelines and continuous quality audits:

```bash
python broken_links_scanner.py https://company.ca -j
```

***

## Technical Frequently Asked Questions

### 1. How do HTTP 404 errors and dead links degrade search engine crawl budget?
Search engine bots allocate a finite request quota to each domain during routine site exploration. Encountering broken links consumes crawl capacity on non-existent endpoints, delaying the indexation of newly published content.

### 2. Why does the scanner execute HTTP HEAD requests followed by GET fallbacks?
The tool initiates checks with lightweight HEAD requests to inspect response status codes without downloading payload bytes. If an endpoint blocks HEAD requests with 403 or 405 codes, the scanner automatically retests via GET to prevent false positives.

### 3. How do broken internal links impair PageRank equity distribution across a website?
Internal navigation links serve as the primary conduits for transferring accumulated authority and semantic relevance across a domain. Dead internal links terminate equity flow prematurely, leaving subordinate pages isolated and underperforming in organic rankings.

### 4. What operational risks are associated with unmaintained broken outbound citations?
Linking to abandoned or hijacked third-party domains exposes users to malicious redirects and undermines site trustworthiness. Modern AI answer engines evaluate outbound citation integrity, discounting resources that cite unreachable endpoints.

### 5. Why is automated link validation critical during domain migrations and cutovers?
System migrations and content reorganisations frequently introduce broken navigational paths and incorrect destination mapping. Automated link auditing catches broken routes immediately, preventing indexation drop-offs before traffic is compromised.

***

## Hyperlink Architecture and Crawl Efficiency Advisory

For multi-market digital portals requiring robust link integrity and alignment with W3C Web Guidelines, consult the engineering team at **TAVARDT**.

***

## Useful Links

* **Corporate Portal:** https://ag.tavardt.com/ca/
* **Diagnostic Suite:** https://tools.tavardt.com/ca/
* **Technical Contact:** https://ag.tavardt.com/ca/contact/

***

### License
Distributed under the MIT License. See the LICENSE file for complete terms.

***

© 2026 TAVARDT. All rights reserved.
