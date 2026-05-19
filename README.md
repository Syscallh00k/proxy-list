
# proxy-list

Auto-updated public proxy list, refreshed every **5 minutes** from 13 sources.

Maintained by [@Syscallh00k](https://github.com/Syscallh00k). Hosted from a Ubuntu VPS running a systemd-timed scraper.

---

## Donations

If this list saves you time, throw a few sats my way. Every bit helps keep the VPS running.

| Coin | Address |

|------|---------|

| **BTC** | `bc1qcul6z4upspzvdhpz2zh4k9xsxz835e07tgdhv9` |

| **LTC** | `ltc1qq968c0s93vp92wye6zprlygfyfx6fsykkn0pe7` |

| **ETH** | `0x2b413b82897B5B70Ce05b70b0Bd2Ba4503CefA54` |

---

## Endpoints

Hit the raw URLs directly — no auth, no rate limits beyond GitHub's CDN.

| Protocol | URL |

|----------|-----|

| HTTP     | `https://raw.githubusercontent.com/Syscallh00k/proxy-list/main/http.txt` |

| HTTPS    | `https://raw.githubusercontent.com/Syscallh00k/proxy-list/main/https.txt` |

| SOCKS4   | `https://raw.githubusercontent.com/Syscallh00k/proxy-list/main/socks4.txt` |

| SOCKS5   | `https://raw.githubusercontent.com/Syscallh00k/proxy-list/main/socks5.txt` |

| All (with scheme prefix) | `https://raw.githubusercontent.com/Syscallh00k/proxy-list/main/all.txt` |

| Last updated timestamp + counts | `https://raw.githubusercontent.com/Syscallh00k/proxy-list/main/last_updated.txt` |

---

## File format

Per-protocol files (`http.txt`, `https.txt`, `socks4.txt`, `socks5.txt`):



1.2.3.4:8080 

5.6.7.8:3128



One `ip:port` per line, sorted by IP octets then port, deduplicated.

`all.txt` includes the scheme prefix: http://1.2.3.4:8080 socks5://5.6.7.8:1080



`last_updated.txt`:

2026-05-14T03:46:34Z http=108645 https=16905 socks4=93515 socks5=125528 total=344593



---

## Sources

Aggregated from 13 publicly available proxy lists. The scraper queries each source, normalizes the output, deduplicates across all sources, and writes per-protocol files.

| # | Source | Type | Notes |

|---|--------|------|-------|

| 1 | [ProxyScrape](https://proxyscrape.com/) | API | Paginated JSON, all protocols |

| 2 | [free-proxy-list.net](https://free-proxy-list.net/) | HTML scrape | HTTP/HTTPS only |

| 3 | [GeoNode](https://geonode.com/free-proxy-list) | API | Paginated JSON, all protocols |

| 4 | [hide.mn](https://hide.mn/en/proxy-list/) | HTML scrape | All protocols, may be Cloudflare-gated |

| 5 | [freeproxy.world](https://www.freeproxy.world/) | HTML scrape | Paginated, all protocols |

| 6 | [openproxylist.xyz](https://api.openproxylist.xyz/) | Plain text API | Per-protocol endpoints |

| 7 | GitHub aggregator lists | Raw text | 12 repos including TheSpeedX, monosans, ProxyScraper, sunny9577, hookzof, mmpx12, roosterkid, prxchk, MuRongPIG, zloi-user, vakhov, proxifly |

| 8 | [spys.me](https://spys.me/) | Plain text | HTTP/HTTPS/SOCKS |

| 9 | [proxyspace.pro](https://proxyspace.pro/) | Plain text | Per-protocol endpoints |

| 10 | [proxyscan.io](https://www.proxyscan.io/) | JSON API | All protocols |

| 11 | [proxy-daily.com](https://proxy-daily.com/) | HTML scrape | HTTP/SOCKS4/SOCKS5 |

| 12 | [advanced.name](https://advanced.name/freeproxy) | Plain text | All protocols |

| 13 | [free.geonix.com](https://free.geonix.com/) | SSR cache API | All protocols, OCR not implemented for obfuscated ports |

---

## Update cadence

- **Refresh interval:** 5 minutes

- **Push strategy:** single rolling commit, force-pushed each cycle (history stays bounded)

- **CDN caching:** `raw.githubusercontent.com` caches ~5 minutes, so consumers may briefly see the previous batch

---

## Disclaimer

These proxies are scraped from public sources. They are:

- **Not verified** — no liveness check is performed; consumers must verify before use

- **Not anonymous-tier guaranteed** — anonymity claims from upstream sources are not validated

- **Not endorsed** — listing here does not imply safety, legality of use, or operator consent

Use at your own risk. Respect the terms of service of any site you route traffic through. This list is provided for research, security testing, and educational purposes.

---

## License

Aggregated data is public. The scraper code and this repo's metadata are released under the MIT License.

