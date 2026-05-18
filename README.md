# katriel-moses/cves

This is where I publish security advisories for vulnerabilities I find and responsibly disclose in open source projects.

Every CVE here was found through manual source code auditing, reproduced with a working proof of concept, privately reported to the maintainer, and only published after a fix was released. No surprise drops, no drama. Just clean responsible disclosure.

---

## Who I am

I'm Katriel Moses, an independent security researcher. I audit open source projects in my spare time, purely because I enjoy it and because I think the people building free software for the rest of us deserve to know when something is wrong with it.

So far I've audited 11 open source projects ranging from smaller tools to projects with over 20k GitHub stars, used by thousands of people daily. Across those audits I've found and reported 5 remote code execution vulnerabilities, most of them the result of chaining multiple lower-severity issues together to reach full command execution. That's the kind of thing automated scanners miss entirely.

---

## What I do and why

Open source projects are the backbone of a huge amount of software that people trust without thinking twice about it. The developers building these projects are often doing it for free, in their own time, and security audits are expensive and most small to mid-sized projects will never get one.

I want to change that, at least a little. My audits are free, no strings attached, with one condition: the project has to be open source.

When I audit a repo I go through the source code manually, looking for logic flaws, unsafe patterns, and vulnerabilities that can be chained into something serious. I write working proof-of-concept exploits for everything I find, report privately with full details, and work with the maintainer through to the fix. Once everything is patched and CVEs are assigned, I publish the advisories here.

At the end of the audit, I also provide a certificate confirming that the project has been reviewed and that all identified vulnerabilities have been addressed, something maintainers can point to as proof that someone looked, found issues, and they got fixed.

---

## What you get out of it

- A full manual source code security audit at no cost
- Private disclosure with detailed reproduction steps for every finding
- CVEs filed and GHSA advisories published once fixes are live
- A certificate of security audit you can reference in your README or documentation
- The ability to tell your users that your project has been independently audited

---

## How it works

1. Reach out with a brief description of your project
2. I'll confirm I can take it on
3. I typically complete the audit within a weekend, two at most
4. Findings go to you privately with full details and working PoCs
5. You patch at your own pace. I'm happy to review the fix too
6. Once everything is resolved, CVEs get assigned and advisories go public here

The whole process is collaborative. I'm not here to embarrass anyone, I'm here to help.

---

## Completed audits

| Project | Stars | Findings | Status |
|---------|-------|----------|--------|
| [jarrodwatts/claude-hud](https://github.com/jarrodwatts/claude-hud), Claude Code statusline plugin | ~20k | 5 (2 High, 3 Medium) | CVEs assigned |
| [tickstep/aliyunpan](https://github.com/tickstep/aliyunpan), Alibaba Cloud Drive CLI client | ~5k | 8 (2 Critical, 4 High, 2 Medium) | CVEs pending |
| [nsf/gocode](https://github.com/nsf/gocode), Go autocompletion daemon for Vim/Neovim/Emacs | ~5k | 5 (2 Critical, 3 High) | CVEs pending |
| [achristmascarl/rainfrog](https://github.com/achristmascarl/rainfrog), terminal database management tool | ~5k | 5 (5 High) | CVEs pending |
| [aaPanel/BaoTa](https://github.com/aaPanel/BaoTa), BaoTa Linux server panel | ~4.4k | 2 (2 High) | CVEs pending |
| [xubiaolin/docker-zerotier-planet](https://github.com/xubiaolin/docker-zerotier-planet), self-hosted ZeroTier planet server | ~3.9k | 5 (1 Critical, 4 High) | CVEs pending |
| [Fredolx/open-tv](https://github.com/Fredolx/open-tv), cross-platform IPTV app | ~3.5k | 6 (1 Critical, 1 High, 4 Medium) | CVEs pending |
| [urwid/urwid](https://github.com/urwid/urwid), Python console UI library | ~3k | 3 (2 High, 1 Medium) | CVEs pending |
| [xyproto/algernon](https://github.com/xyproto/algernon), pure-Go web server with Lua scripting | ~3k | 4 (1 Critical, 3 High) | ✅ Patched in v1.17.6 |
| [Cp0204/quark-auto-save](https://github.com/Cp0204/quark-auto-save), Quark cloud drive auto-save tool | ~2.3k | 2 (1 High, 1 Medium) | CVEs assigned |
| [JuliusBrussee/cavekit](https://github.com/JuliusBrussee/cavekit), Claude Code build orchestration plugin | growing | 5 (3 Critical, 2 High) | CVEs pending |

---

## Published CVEs

| CVE | Project | Severity | Summary |
|-----|---------|----------|---------|
| [CVE-2026-43981](./algernon/CVE-2026-43981.md) | algernon | High | Race condition in handle() shared LState, DoS under concurrent load |
| [CVE-2026-43982](./algernon/CVE-2026-43982.md) | algernon | High | Path traversal file write via savein(), arbitrary write outside web root |
| [CVE-2026-45228](./quark-auto-save/CVE-2026-45228.md) | quark-auto-save | Medium | Stored XSS via System Configuration (push_config keys) |
| [CVE-2026-45229](./quark-auto-save/CVE-2026-45229.md) | quark-auto-save | High | Mass assignment via POST /update leading to credential takeover |
| [CVE-2026-47090](./claude-hud/CVE-2026-47090.md) | claude-hud | Low | Terminal injection via OSC 8 hyperlinks using unsanitized cwd/branchUrl values |
| [CVE-2026-47091](./claude-hud/CVE-2026-47091.md) | claude-hud | Medium | Path traversal via transcript_path allows arbitrary local file read |
| [CVE-2026-47092](./claude-hud/CVE-2026-47092.md) | claude-hud | High | COMSPEC env var hijacking leads to arbitrary command execution on Windows |
| More coming soon | | | ~13 CVEs currently in the assignment pipeline across the projects above |

---

## Get in touch

If you maintain or contribute to an open source project and want it audited, just reach out. It costs nothing and the worst case is you get a clean bill of health.

**Email:** [katriel@rootaccess.tech](mailto:katriel@rootaccess.tech)  
**LinkedIn:** [linkedin.com/in/katriel-moses](https://linkedin.com/in/katriel-moses)

I'll always respond. If the project is open source, I'll take it on.

---

*All research is conducted on isolated local environments. No production systems are ever accessed. All disclosures follow a responsible disclosure process: reported privately to maintainers first, published only after fixes are released and CVEs are assigned.*
