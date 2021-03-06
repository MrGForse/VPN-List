# VPN-List
A list of domains that popular VPNs use for authentication and other communication. Due to the nature of VPNs, it's best not to rely on DNS to block and instead use a proxy server such as SquidGuard on a firewall appliance.

This list is a sanitized dump of the blocklist I've been building at work to mitigate VPN usage. Blocking these hosts will prevent access to authentication for VPNs in most cases.

VPNs are quite difficult to block, so you can either use Layer 7 filtering to intelligently identify VPNs (This will break a lot of legitimate services e.g. Wi-Fi Calling) or only allow ports 80 and 443 (Having internal DNS servers which do have access to port 53) while decrypting and inspecting (or validating) SSL connections, however this will also break a lot of legitimate services.

Denying literal IP hosts will also mitigate/disable many VPNs using HTTPS/TCP 443 or HTTP/TCP 80. I'd also recommend blocking/disabling QUIC as any QUIC requests will bypass your proxy. You can disable QUIC by blocking UDP 80 & UDP 443 in your UTM/Firewall, and you can also set Group Policies or Google Admin Policies to disable this in Google Chrome.

# Important Note for Educational Institutions:
You must comply with local safeguarding laws set by your state or country. You cannot solely use this list as your only mitigation against VPN usage on your networks. You must use a compliant UTM, Web Proxy, Layer 7 Firewall or other safeguarding solution in addition to this list.

You may also have some additional success in mitigating this risk by educating those dependent on you for safeguarding them. You can tackle this issue with technology, however, at the end of the day it is a behavioural issue which should be treated the same way as any other breach of conduct or policy. A two-pronged approach is best, I have found.

# This list breaks:
* WindScribe
* Betternet
* X-VPN
* PrivateInternetAccess
* Many Chrome/Firefox VPN Plugins
* YouTube "Unblocker" plugins
* Etc.
