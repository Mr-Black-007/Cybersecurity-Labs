Project: Network Hardening & Privacy Baseline
1. Objective

The goal of this project was to establish a high-performance privacy baseline for daily internet usage. The focus was on eliminating ISP-level data collection and tracking without the typical performance degradation or "CAPTCHA tax" associated with traditional VPN services.


2. Problem Statement

    ISP Visibility: Direct connections allow Internet Service Providers to monitor, log, and profile user activity through DNS queries and destination IP tracking.

    VPN Friction: Traditional VPNs often introduce significant latency and trigger frequent automated bot detection (CAPTCHAs), making them impractical for "always-on" regular internet usage.

    Android Limitations: Android OS restricts the use of multiple VPN-based services. This creates a conflict for users who require encrypted routing (WARP) while maintaining custom DNS-level filtering (AdGuard).


3. Technical Implementation
Desktop (Windows 11 & Linux)

I utilized the official Cloudflare WARP client to establish a system-wide encrypted tunnel. This configuration ensures that all outbound traffic is encapsulated and routed through the Cloudflare global network, masking the final destination from the local ISP.
Mobile (Android)

To resolve the conflict between encryption and DNS filtering on Android, I bypassed standard app installations in favor of a manual configuration:

    WireGuard Integration: Generated a custom WireGuard profile (.conf) that combines Cloudflare WARP endpoints with AdGuard DNS resolvers.

    Unified Tunnel: This allows for encrypted routing and aggressive ad/tracker blocking within a single tunnel, successfully circumventing the Android system limitation of one active VPN service.


4. Verification & Audit

The integrity of the tunnel was verified using diagnostic tools to ensure zero data leakage to the local ISP.

    DNS Leak Analysis: verified that DNS requests are intercepted by AdGuard and infrastructure providers like Datacamp/Cogent, rather than the local ISP.

    Connectivity Debugging: Audited the connection status via the Cloudflare debug interface:

        Exposed State: In a raw connection, traffic is fully visible to the ISP and routed through local gateways such as Chennai (MAA) or Delhi (DEL).

        Hardened State: Once the tunnel is active, the ISP only sees an encrypted pipe to a Datacamp or Cloudflare node. Traffic is handled by secure data centers in Singapore (SIN) or Mumbai (BOM).


5. Summary of Results

This configuration provides a frictionless privacy solution. By moving to a manual WireGuard setup, I achieved a secure "always-on" environment that prevents ISP tracking while maintaining native-like browsing speeds and avoiding the automated friction common in the VPN industry.

Tools Used: Cloudflare WARP, WireGuard, AdGuard DNS | DNSLeakTest Investigator: Adarsh
