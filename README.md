# Wireshark (wireshark)
Wireshark is the world's foremost and widely-used free and open-source network protocol analyzer. It lets you capture and interactively browse the traffic running on a computer network. Wireshark provides a powerful dissector framework with a Lua scripting API, C/C++ plugin architecture, TShark command-line tools, and the libwireshark library for developers building network analysis tools.

**URL:** [https://www.wireshark.org](https://www.wireshark.org)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags:

 - Debugging, Network Analysis, Open Source, Packet Capture, Protocol Analysis, Security

## Timestamps

- **Created:** 2025-01-08
- **Modified:** 2026-05-03

## APIs

### Wireshark
Wireshark is a free and open-source network protocol analyzer that captures and interactively browses network traffic. It supports hundreds of protocols, runs on multiple platforms, and provides deep inspection of packets. Developers can extend Wireshark through its Lua scripting API, C/C++ dissector plugins, Extcap plugin interface, and the Wiretap library for custom capture file formats.

**Human URL:** [https://www.wireshark.org](https://www.wireshark.org)

#### Tags:

 - Debugging, Extcap, Lua Scripting, Network Analysis, Open Source, Packet Capture, Protocol Analysis, Plugins

#### Properties

- [Documentation](https://www.wireshark.org/docs/)
- [API Reference (Developer's Guide)](https://www.wireshark.org/docs/wsdg_html_chunked/)
- [Getting Started (User Guide)](https://www.wireshark.org/docs/wsug_html_chunked/)
- [Dissector Plugin API (C/C++)](https://www.wireshark.org/docs/wsdg_html_chunked/ChapterDissection.html)
- [Lua API Reference](https://www.wireshark.org/docs/wsdg_html_chunked/wsluarm.html)
- [Downloads](https://www.wireshark.org/download.html)

## Common Properties

- [Website](https://www.wireshark.org)
- [Documentation](https://www.wireshark.org/docs/)
- [Blog](https://blog.wireshark.org)
- [FAQ](https://www.wireshark.org/faq.html)
- [GitHub](https://github.com/wireshark/wireshark)
- [GitLab](https://gitlab.com/wireshark/wireshark)
- [Support](https://ask.wireshark.org)
- [Downloads](https://www.wireshark.org/download.html)
- [Release Notes](https://www.wireshark.org/docs/relnotes/)
- [Forum](https://www.wireshark.org/lists/)

## Features

| Name | Description |
|------|-------------|
| Packet Capture | Capture live network traffic from multiple interfaces simultaneously using libpcap/Npcap. |
| Deep Packet Inspection | Analyze hundreds of protocols with full decode of packet fields and values. |
| Display Filters | Powerful filter language for drilling into captured traffic. |
| Lua Scripting | Extend Wireshark with custom dissectors, listeners, and menus using the Lua API. |
| Dissector Plugins | Write C/C++ plugins to add support for new protocols. |
| TShark CLI | Command-line version of Wireshark for scripting and automation. |
| Extcap Interface | Plugin API to add custom capture sources to Wireshark. |
| Wiretap Library | Library for reading and writing capture file formats including pcap and pcapng. |

## Use Cases

| Name | Description |
|------|-------------|
| Network Troubleshooting | Diagnose latency, packet loss, and protocol errors in live or captured traffic. |
| API Traffic Debugging | Inspect raw HTTP, gRPC, and WebSocket API requests and responses at the packet level. |
| Protocol Development | Develop and test new network protocols using Wireshark dissectors. |
| Security Analysis | Analyze network traffic for intrusion indicators and malicious patterns. |
| Education | Learn networking concepts by capturing and examining real protocol exchanges. |

## Integrations

| Name | Description |
|------|-------------|
| TShark | Command-line packet analyzer that uses the same dissection engine as Wireshark. |
| dumpcap | Minimal capture utility used by Wireshark and TShark. |
| editcap | Utility for editing and converting capture files. |
| Lua | Scripting language embedded in Wireshark for custom protocol dissectors. |
| libpcap/Npcap | Packet capture libraries used by Wireshark on Unix and Windows respectively. |

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
