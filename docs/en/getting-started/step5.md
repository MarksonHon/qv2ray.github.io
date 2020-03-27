---
title: Further Steps
---

# Further Steps

If you are lucky enough, you may now be able to surf the Internet freely. Here are some optional steps that you can follow, to make your experience with Qv2ray better.

## Joining Qv2ray User Group
We suggest you join our [Qv2ray User Group](https://t.me/qv2ray) at [Telegram](https://telegram.org/). Here you can chat directly with Qv2ray developers, and also the great Qv2ray users. For usage problems, it is always more efficient to discuss them in the group, than opening up one issue on GitHub. 

Also, optionally, you may subscribe [Qv2ray Outpost](https://t.me/qv2ray_outpost) channel at Telegram, if you don't like to talk too much or even show up. We will push news updates of Qv2ray, and even send polls that maybe decides Qv2ray's fate! Make sure you don't miss it.


## Tweaking Routing Schemes
By default, Qv2ray will be set to **bypass the traffic of China mainland**, according to `geosite.dat` and `geoip.dat` from V2Ray core, thus it it not necessary to configure some awkward PAC rules. You can override this default setting in the **Preference Window**, by simply turing off this function in tab **Connection Settings**.

However, sometimes, these rules won't always apply. For example, you have a special proxy for [bilibili](https://bilibili.com/) that unlocks the Hong Kong/Macau/Taiwan episodes. Since bilibili is a China mainland website, by default, the traffic won't go through the proxy, and that causes you problem. The solution is using our **Advanced Route Settings** in the **Preference Window**.

A valid route setting scheme is basically a 2x3 routing rule matrix. Syntax for the rules can be found in [RuleObject Documentation](https://v2ray.com/chapter_02/03_routing.html#ruleobject) from V2Ray Official Website. Here, if we want to force bilibili go through proxy, we just write a rule `domain:bilibili.com` at `(Domain, Proxy)` position. 

There are other advanced usages of routing schemes. If you are interested, try explore more into it.

## Sharing Proxy over Local Network

For the sake of safety, by default, Qv2ray will only listen on `127.0.0.1`, that is to say, only your own machine is allowed to use the proxy. If you want to share your proxy over your local network, there are changes to be made.

The most simple and overkill method is to change the listen address from `127.0.0.1` to `0.0.0.0`, which will allow all incoming connections to your little proxy. 

However, this is **not as safe**, since your proxy can be easily abused and attacked by others. To prevent this, you have to either shield yourself under NAT (for example, using a trusted router and don't expose your proxy ports), or setup a firewall to block the unwanted addresses (iptables, and etc).

You may encounter connectivity problems when sharing proxy. Here are some troubleshooting tips:
 - allow V2Ray core to listen on `0.0.0.0` in Windows Firewall
 - disable Intranet Isolation / AP Isolation on your router

