<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a1b26,100:414868&height=200&section=header&text=Pratham%20Agarwal&fontSize=48&fontColor=c0caf5&animation=fadeIn&fontAlignY=35&desc=Security%20tooling%20and%20full-stack%20builds&descAlignY=55&descSize=18&descColor=a9b1d6" width="100%" alt="header" />

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&pause=1000&color=C0CAF5&background=1A1B26&center=true&vCenter=true&width=740&lines=Built%3A+ransomware+detector%2C+entropy+%2B+rename-velocity;Built%3A+async+API+security+scanner%2C+16+OWASP+categories;Built%3A+Wazuh+SIEM+%2B+Gemini-based+alert+triage;Built%3A+multi-vendor+SD-WAN+config+auditor)](https://github.com/pratham2104)

[![GitHub](https://img.shields.io/badge/GitHub-pratham2104-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/pratham2104)

</div>

## About

I build security tooling and test it against real, self-built targets instead of tutorials. Recent projects include a behavioral ransomware detector (entropy plus rename-velocity, not signatures), an async API vulnerability scanner mapped to the OWASP API Top 10 and MITRE ATT&CK, an LLM-based SIEM triage agent validated against ground-truth findings from my own scanner, and a multi-vendor SD-WAN config auditor. I also finished the Google Cybersecurity Professional Certificate and do full-stack web work in Node, Express, PostgreSQL, and Next.js. Most of the security repos follow the same pattern: ship a detector, then run it against something real and write up whatever breaks.

## Tools I Know

> Pulled from what's actually used across these repos, not a wishlist

<table>
  <tr>
    <td align="center" width="96">
      <img src="https://techstack-generator.vercel.app/python-icon.svg" alt="Python" width="65" height="65" />
      <br>Python
    </td>
    <td align="center" width="96">
      <img src="https://techstack-generator.vercel.app/js-icon.svg" alt="JavaScript" width="65" height="65" />
      <br>JavaScript
    </td>
    <td align="center" width="96">
      <img src="https://techstack-generator.vercel.app/java-icon.svg" alt="Java" width="65" height="65" />
      <br>Java
    </td>
    <td align="center" width="96">
      <img src="https://skillicons.dev/icons?i=html" width="48" height="48" alt="HTML" />
      <br>HTML
    </td>
    <td align="center" width="96">
      <img src="https://skillicons.dev/icons?i=css" width="48" height="48" alt="CSS" />
      <br>CSS
    </td>
    <td align="center" width="96">
      <img src="https://skillicons.dev/icons?i=git" width="48" height="48" alt="Git" />
      <br>Git
    </td>
  </tr>
  <tr>
    <td align="center" width="96">
      <img src="https://skillicons.dev/icons?i=nodejs" width="48" height="48" alt="Node.js" />
      <br>Node.js
    </td>
    <td align="center" width="96">
      <img src="https://skillicons.dev/icons?i=express" width="48" height="48" alt="Express" />
      <br>Express
    </td>
    <td align="center" width="96">
      <img src="https://skillicons.dev/icons?i=nextjs" width="48" height="48" alt="Next.js" />
      <br>Next.js
    </td>
    <td align="center" width="96">
      <img src="https://techstack-generator.vercel.app/restapi-icon.svg" alt="REST API" width="65" height="65" />
      <br>REST API
    </td>
    <td align="center" width="96">
      <img src="https://skillicons.dev/icons?i=postgres" width="48" height="48" alt="PostgreSQL" />
      <br>PostgreSQL
    </td>
    <td align="center" width="96">
      <img src="https://skillicons.dev/icons?i=redis" width="48" height="48" alt="Redis" />
      <br>Redis
    </td>
  </tr>
  <tr>
    <td align="center" width="96">
      <img src="https://skillicons.dev/icons?i=tailwind" width="48" height="48" alt="Tailwind CSS" />
      <br>Tailwind CSS
    </td>
    <td align="center" width="96">
      <img src="https://techstack-generator.vercel.app/github-icon.svg" alt="GitHub" width="65" height="65" />
      <br>GitHub
    </td>
    <td align="center" width="96">
      <img src="https://skillicons.dev/icons?i=vercel" width="48" height="48" alt="Vercel" />
      <br>Vercel
    </td>
    <td align="center" width="96">
      <img src="https://skillicons.dev/icons?i=supabase" width="48" height="48" alt="Supabase" />
      <br>Supabase
    </td>
    <td align="center" width="96">
      <img src="https://skillicons.dev/icons?i=linux" width="48" height="48" alt="Linux" />
      <br>Linux
    </td>
    <td align="center" width="96">
      <img src="https://skillicons.dev/icons?i=jest" width="48" height="48" alt="Jest" />
      <br>Jest
    </td>
  </tr>
</table>

## Featured Projects

### [Ransomware Behavioral Detector](https://github.com/pratham2104/ransomware-behavioral-detector)
Watches for the *behavior* ransomware produces on disk (a rename-velocity spike plus a jump in file-content entropy) instead of matching known malware signatures, paired with a self-written Fernet/AES simulator that tests the whole pipeline end to end. Testing it against itself turned up two real bugs: an entropy check that looked wired up but silently never fired, because base64-encoded ciphertext capped entropy at 6.0 bits per byte, well below the 7.2 threshold, and a process-killer with no allowlist that killed macOS's own iCloud sync daemon.

### [API Attack Surface Auditor](https://github.com/pratham2104/api-attack-surface-auditor)
Async Python scanner covering 16 vulnerability categories (OWASP API Top 10 and more), with every finding mapped to MITRE ATT&CK and scored with CVSS. Version 6 added OpenAPI auto-discovery, so it no longer needs a hardcoded route list. I ran it against a self-built Node/Express and PostgreSQL wellness platform, and it confirmed a real CVSS 9.8 SQL injection.

### [AI SIEM Triage Agent](https://github.com/pratham2104/ai-siem-triage-agent)
A self-hosted Wazuh SIEM, provisioned from scratch on an Oracle Cloud ARM VM, feeds real alerts (generated by the API Attack Surface Auditor scanning a live target) to Google Gemini for structured triage. I built it to measure whether the AI's triage output actually holds up against independently verified ground truth, since wiring an LLM to a SIEM is the easy part.

### [SD-WAN Misconfiguration Scanner](https://github.com/pratham2104/sdwan-misconfiguration-scanner)
Static-analysis auditor for Fortinet, Versa Networks, and HPE Aruba SD-WAN configs. 38 rules cover IPsec/IKE crypto, admin access, SNMP, and firewall policy, each mapped to MITRE ATT&CK and CVSS v3.1 with a remediation command. I tested it against a real 10,684-line production FortiGate config.

## GitHub Stats

<div align="center">

<img src="https://github-stats-extended.vercel.app/api?username=pratham2104&show_icons=true&theme=tokyonight&hide_border=true&count_private=true" alt="pratham2104's GitHub stats" height="165" />
<img src="https://github-stats-extended.vercel.app/api/top-langs/?username=pratham2104&layout=compact&theme=tokyonight&hide_border=true" alt="Top languages" height="165" />

<img src="https://streak-stats.demolab.com?user=pratham2104&theme=tokyonight&hide_border=true" alt="GitHub streak stats" />

</div>

## Contribution Snake

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/pratham2104/pratham2104/output/github-contribution-grid-snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/pratham2104/pratham2104/output/github-contribution-grid-snake.svg" />
  <img alt="Contribution snake animation" src="https://raw.githubusercontent.com/pratham2104/pratham2104/output/github-contribution-grid-snake.svg" width="100%" />
</picture>

</div>

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:414868,100:1a1b26&height=120&section=footer" width="100%" alt="footer" />

![Profile views](https://komarev.com/ghpvc/?username=pratham2104&color=414868&style=flat-square&label=Profile+views)

</div>
