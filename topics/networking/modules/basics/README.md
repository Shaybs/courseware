# Basics

<!--TOC_START-->
## Contents
- [Overview](#overview)
- [Network Architecture](#network-architecture)
	- [Network topology](#network-topology)
	- [P2P](#p2p)
- [Network Characteristics](#network-characteristics)
- [Network Types](#network-types)
	- [Network Spatial Scope](#network-spatial-scope)
	- [The Internet](#the-internet)
	- [The World Wide Web](#the-world-wide-web)
	- [Web access](#web-access)
		- [URI](#uri)
		- [URL](#url)
		- [Encoding](#encoding)
- [Networking Tools](#networking-tools)
	- [`nslookup`](#nslookup)
	- [`ping`](#ping)
- [Tasks](#tasks)

<!--TOC_END-->
## Overview
A network is essentially a web of distributed communication between entities.

At the lowest level, networks facilitate the sharing of information.

The internal and external transfer of information is crucial for this task.

The most well-known network is the **Internet**, which, though well-known, is often poorly-understood.

It arose out of a need for institutions to be accessible to, communicate with, and share information with each other.

## Network Architecture
An example of typical network architecture is shown below:

```text
          ┌────────[Router]────────┐
       [Switch]                 [Switch]
    ┌─────┴─────┐            ┌─────┴─────┐
  [Node]      [Node]       [Node]      [Node]
```

The functions of these basic network components are listed below:

| Component | Function |
|-|-|
| Router | Forwards data and directs network traffic |
| Switch | Connects devices; receives and processes packets from a router to send to a device |
| Node | A device; sends packets to a switch to forward to a router; receives and processes packets from a switch |

There are also several other components that might be commonly found in a network:

| Component | Function |
|-|-|
| Cable | Direct connectivity between any network components |
| Signal |  Wireless connectivity between any network components |
| Network Interface Controller (NIC )| Physically receives data from a network |
| Host adapter | Connects a host system to other network/storage devices |
| Gateway | Allows for data transfer between networks |
| Network bridge | Aggregates mutliple networks together |
| Hub | Connects multiple devices together onto a single network |

There are a myriad of other physical, wireless, and hybrid network devices.

### Network topology
Topology refers to the way a network is organised, both physically and logically.

Originally, all networks were wired, and therefore usually adhered to one of a few specific network topologies due to limitations on physical hardware.

**Bus**
```text
    ┌─────┬─────┐
  [Node][Node][Node]
```
**Ring**
```text
  ┌[Node]─[Node]┐
  |             |
  |             |
  |             |
  └[Node]─[Node]┘
```
**Star**
```text
  [Node] [Node]
      \   /
      [Hub]
      /   \
  [Node] [Node]
```
**Mesh**
```text
  ┌[Node]─[Node]┐
  |    \   /    |
  |     ───     |
  |    /   \    |
  └[Node]─[Node]┘
```
**Tree**
```text
          ┌────────[Node]────────┐
        [Node]                 [Node]
    ┌─────┴─────┐          ┌─────┴─────┐
  [Node]      [Node]     [Node]      [Node]
```

### P2P
Most **Hybrid** topologies combine several of these styles together.

Wireless technology is heavily-hybridised by design: most Internet-enabled devices are so interconnected to each other that network topology has deprecated to the level of describing much smaller, wired, or home/office network architecture.

These are **peer-to-peer** (P2P) networks: every node can exchange data with any other node, with each node acting both as a client (receiving information) and a server (sending information).

## Network Characteristics
Networks always operate on the basis of providing seamless interconnectivity between devices.

Therefore, there are a number of characteristics by which all networks must adhere to, in some capacity.

The most important six ways are listed below: 

| Characteristic | |
|-|-|
| High capacity | Can the network support significant amounts of data transfer? |
| Fast speeds | How quickly does data move between nodes? |
| Low latency | How long does data take to move between nodes? |
| High availability | How many nodes can supply the same data? |
| Redundancy | How many backup nodes are there in the case of network failure? |
| Security | How safe is the network's data? Is the architecture secure from attack? |

## Network Types
Networks are broadly classified into two types: **LAN** (**L**ocal **A**rea **N**etwork) and **WAN** (**W**ide **A**rea **N**etworks).

The key characteristics by which we can differentiate between them are as follows:

| Characteristic | LAN | WAN |
|-|-|-|
| Geographic distribution | Small; used for e.g. university campuses | Large; used for e.g. cities |
| Data transmission rate | Fast; gigabits | Slow; megabits |
| Error rate | Lower; due to local connectivity | Higher; as a result of distribution |
| Communication link | 'In-house'; e.g. coaxial cables, fibre-optics, ethernet | External; e.g. phone lines, microwave links, satellite channels |
| Ownership | Single; usually a single organisation or individual | Multiple; essentially several interconnecting LANs |
| Communication cost | Lower; simpler operation allows for reliability | Higher; some aspects of operation may be leased or unreliable |

These differences show the difference in scale between LAN and WAN - while LAN is a small, interconnected collection of nodes usually operated by a single entity across a small area, WAN connects several LAN together to allow for wider, though less reliable, communication across multiple entities.

### Network Spatial Scope
There are a number of other network types, according to specific circumstances.

The following table gives brief explanations of each network type in practice:

| Name | Acronym | Function | e.g. |
|-|:-:|-|-|
| Nanoscale | `nano` | Electromagnetic and molecular data transmission | medical nanotechnology |
| Near-Field Communication | `NFC` | Portable dual-device communication | contactless payment |
| Body Sensor Network | `BSN` | Wearable computing devices | smartwatches, implants |
| Personal | `PAN` | Individual workspace connections | Bluetooth, wireless USB |
| Near-me | `NAN` | Proximity-based connections | mobile technology - masts serve multiple carriers |
| (Wireless) Local | `(W)LAN` | Some institution or individual usage | Ethernet, WiFi |
| Metropolitan | `MAN` | Interconnected LANs in a geographical area via endpoint connections | Silicon Valley |
| Wide | `WAN` | Region-spanning network transmitting data between multiple entities | frame relays |
| Cloud | `Cloud` | Massively distributed, using mutliple data centres in multiple geographic regions as a secure connector of endpoints | GCP, AWS, Azure |
| Internet Area | `IAN` | Direct Cloud-based endpoint connection over IP | (conceptual) |
| Interconnected Network | `Internet` | Global system of interconnected networks | TCP/IP, World Wide Web |

### The Internet
As the largest telecommunications network (its name is literally shortened from **inter**connected **net**work), the Internet is the best example of a WAN taken to its logical extreme.

Its early form was commissioned by the United States as a way of building robust, fault-tolerant communication between networks, and has exponentially expanded ever since.

As the decentralised and distributed global system of interconnected networks, it uses a series of protocols, most notably the Transmission Control Protcol (TCP) and Internet Protocol (IP), to provide end-to-end data communication to every node which connects to it.

### The World Wide Web
The Internet and the World Wide Web are often conflated expressions, though they are vastly different.

While the Internet is a *networking infrastructure* - a network of networks in which any computer can communicate with another computer - the Web is simply an *information-sharing system* which uses the Internet as its base.

Web services mostly use Hypertext Transfer Protocol (HTTP) to transmit data between nodes, which is usually presented in some form of markup, such as HTTP.

Browsers help to facilitate that data transfer, but the Web itself is one of many vehicles which use the Internet as its basis.

### Web access
Accessing data through the Web is facilitated by using a (**U**niform **R**esource **I**ndicator).

URI is used for all information which flows across the Web: every Web resource must have a specific string of characters which unambiguously define where that particular object is.

For specific Web pages, a Web address, or URL (**U**niform **R**esource **L**ocator) specifies its location on a computer network and mechanism for retrieving it.

Thus, a URL is simply a more specific type of URI.

#### URI
The URI generic syntax consists of a hierarchical sequence of five components:
```text
  URI = scheme:[//authority]path[?query][#fragment]
```
where the authority component divides into three subcomponents:
```text
  authority = [userinfo@]host[:port]
```
As each URI begins with a scheme name that refers to a specification for assigning identifiers within that scheme, URIs can take multiple forms:
```text
  mailto:John.Doe@example.com
  └─┬──┘ └────┬─────────────┘
  scheme     path
```
```text
  tel:+1-816-555-1212
  └┬┘ └──────┬──────┘
  scheme    path
```
```text
  telnet://192.0.2.16:80/
  └─┬──┘   └─────┬─────┘│
  scheme     authority  path
```
```text
  urn:oasis:names:specification:docbook:dtd:xml:4.1.2
  └┬┘ └──────────────────────┬──────────────────────┘
  scheme                    path
```

#### URL
On the other hand, a URL is more specific, and usually conforms a much more varied specification:
```text
          userinfo       host      port
          ┌──┴───┐ ┌──────┴──────┐ ┌┴┐
  https://john.doe@www.example.com:123/forum/questions/?tag=networking&order=newest#top
  └─┬─┘   └───────────┬──────────────┘└───────┬───────┘ └───────────┬─────────────┘ └┬┘
  scheme          authority                  path                 query           fragment
```

#### Encoding
Of the ASCII character set, the characters `: / ? # [ ] @` are reserved for use as delimiters of the generic URI components.

If you wanted to use any of these in the 'plaintext' areas of a URI, such as by appending an email address to a URI, they would need to be percent-encoded.

For instance `%3F`may appear in certain sections of a URL for a `?`.

Occasionally, `&` may also appear as `&amp` for similar reasons.

## Networking Tools
Two of the most basic tools for seeing networking in action are `nslookup` and `ping`.

Both are lookup tools which check the availability of a host.

### `nslookup`
`nslookup` (name server lookup) is a network administration tool on the command-line, which directly queries the Domain Name System (DNS) to obtain domain name or IP address mapping.

Here, we can check for the **IP address** of a particular Web site using `nslookup`:

```cmd
  C:\Windows\system32>nslookup example.com
  Server:  dns.google
  Address:  8.8.8.8

  Non-authoritative answer:
  Name:    example.com
  Addresses:  2606:2800:220:1:248:1893:25c8:1946
            93.184.216.34
```

This gives us some useful information about `example.com`:

- The server which `example.com` is hosted on, which is under Google's DNS jurisdiction at `dns.google`.
- Its IPv4 address, which is `93.184.216.34`.
- Its IPv6 address, which is `2606:2800:220:1:248:1893:25c8:1946`.

The `non-authoritative answer` we see just tells us that `nslookup` is querying DNS records kept on external servers, rather than pinging the entire global DNS system directly.

The two IP addresses refer to the Internet Protocol we mentioned earlier, and just shows us the unique location of a resource (in this case, the `example.com` Web site) across the entire Internet.

More information on IP addresses can be found in the [IP Module](../ip/README.md).
<!--issue-415-->

### `ping`
We use `ping` to query an IP address so as to check its availability:

```cmd
  C:\Windows\system32>ping 93.184.216.34
```

We could also indirectly ping the URL `example.com`:

```cmd
  C:\Windows\system32>ping example.com
```

We receive two outputs.

The first output is a response to each ping we send to `example.com` (a standard `ping` request pings the server 4 times) in the form of a small **packet** of data:

```cmd
  Pinging 93.184.216.34 with 32 bytes of data:
  Reply from 93.184.216.34: bytes=32 time=81ms TTL=51
  Reply from 93.184.216.34: bytes=32 time=79ms TTL=51
  Reply from 93.184.216.34: bytes=32 time=78ms TTL=51
  Reply from 93.184.216.34: bytes=32 time=78ms TTL=51
```

The second output counts the packets successfully sent and received, and counts any that might be lost.

The output of a successful `ping` request typically looks like this:
```cmd
  Ping statistics for 93.184.216.34:
      Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
  Approximate round trip times in milli-seconds:
      Minimum = 78ms, Maximum = 81ms, Average = 79ms
```

Occasionally, due to network failures or other connectivity issues, requests may simply fail to be sent from a node or received by a server.

A failed `ping` request typically looks like this:
```cmd
  C:\Windows\system32>ping en.wikipedia.org

  Pinging dyna.wikimedia.org [91.198.174.192] with 32 bytes of data:
  Request timed out.
  Request timed out.
  Request timed out.
  Request timed out.

  Ping statistics for 91.198.174.192:
      Packets: Sent = 4, Received = 0, Lost = 4 (100% loss),
```

This is an excellent way to check whether a server is 'up' or 'down', as well as average connection speeds between your machine and the server.

## Tasks
### See how NFC works with NFC Tools
*NB: this task will only work on NFC-enabled phones - if you can use contactless with your phone then you can try this Task.*

Here, we can see an example of NFC in-action using the *NFC Tools* app ([Apple](https://apps.apple.com/us/app/nfc-tools/id1252962749) / [Android](https://play.google.com/store/apps/details?id=com.wakdev.wdnfc&hl=en_US)).

Once it's installed, try holding your tag to your phone's reader.

You should see some pretty cool info pop up in the app - your tag's info should be very similar:

![NFCTools tag response](https://i.imgur.com/0G2z7SP.jpg)

When you raise your tag to an NFC reader, like the reader on the door to the academy, it creates a small, but very specific network connection which allows the door to open.

This tag's network protocol is `ISO-14443-3A`, and follows these steps every time it comes into contact with an NFC reader:

![ISO-14443-3A activation](https://www.dummies.com/wp-content/uploads/tag-activation.jpg)

The door reader is a **Proximity Coupling Device (PCD)**, while the tag is a **Proximity Inductive Coupling Card (PICC)**.

1. The door reader sends a radio signal to its immediate proximity, using a 7-bit command called a **Request (REQA)**.
2. The chip embedded within the card is given the tiny amount of energy needed from that Request to send back its own signal - an **Answer to Request (ATQA)** block. Our ATQA block contains a single command: `0x0002`, and the tag's **Unique Identifier (UID)**.
3. A collision - where two or more tags respond to the door reader - may occur if there is more than one card in range. If a collision happens, the door reader will send out a **SELECT** request which includes a portion (**prefix**) of one of the tags' specific UIDs.
4. If collisions still happen, the door reader will send out more and more specific SELECT signals, using longer UID prefixes, until only one tag responds.
5. The selected tag will then respond with a **Select Acknowledgement (SAK)**, which activates the door reader. Our SAK contains the command `0x18`, which in this case will deactivate the electromagnets holding the door closed.
6. The door reader will continue to be activated until it receives a **HALT** command from the tag. In our case, this happens within a second of the SAK being transmitted. 

### See how PAN works with Bluetooth tethering
*NB: this task will only work with Bluetooth-enabled phones and desktops.*

PAN is essentially a short-wave, low-power radio frequency. It reaches further than NFC does, but only to a range of ~10m.

Bluetooth is the most well-known form of PAN - it was developed as a way of bringing together multiple wireless technologies under a single communication protocol. [This video explains how Bluetooth got its name.](https://www.youtube.com/watch?v=VdmQp9M9jUo)

For this task, turn on Bluetooth discovery on your device, and see how many devices in the room it picks up.

Connect to another device in the room - ideally another delegate's phone - and try to send [this image](https://yt3.ggpht.com/a/AGF-l79R65oC-kUKQQii1-zvefpjRvrSYbITqYgD-w=s900-mo-c-c0xffffffff-rj-k-no) to them.

(Depending on your device, there may be a specific option to send files via Bluetooth on your phone).

Even though everybody else is trying to do this at the same time, there shouldn't be much interference.

What's happening under the hood is very similar to what we've already seen for NFC.

Bluetooth transmission works in essentially the same way as NFC, but transmits its signals along the **ISM** frequency band set aside for **i**ndustrial, **s**cientific and **m**edical devices, which operates between 2.402 and 2.480 GHz.

Bluetooth devices avoid interfering with any other devices operating on this frequency band by using **spread-spectrum frequency hopping**. Each device will randomly select 79 different frequencies from a designated range within the ISM band, swapping around which one it uses 1600 times per second.

Bluetooth devices work through addresses, much in the same way as NFC.

When two Blueooth devices connect, they share a fraction of the ISM band to communicate on, with both devices allowing for incoming connections from a particular address. When you turn on your device, it will send radio signals asking for a response from any units with an address in a particular range.

Since other devices around have addresses in the range, it responds, and a PAN is formed.

Even if one of these devices should receive a signal from another system, it will ignore it since it's not from within the network.

Combining this method with an extremely weak transmission signal allows for multiple Bluetooth devices to operate in tandem without major interference.

Any two devices which happen to attempt using the same frequency to communicate would only experience issues for a fraction of a second.

Since each PAN hops randomly through the available frequencies, all of the PANs we create within this room are completely separated from one another.

However, if a multitude of Bluetooth devices are operating at the same time in a packed space, the interferences become more obvious when they do arise.

This is why on a packed tram, everybody's Bluetooth earbuds will crackle more than usual - though the PANs are prevented from accepting incoming connections from outside the network, the ISM band itself is full of devices with overlapping frequency ranges.

### Categorise each section of a long URL

For this task, navigate to [this](https://smile.amazon.co.uk/gp/product/B07HRHM8F3/ref=ox_sc_saved_title_1?smid=A3P5ROKL5A1OLE&psc=1) Amazon item listing.

Categorise the URL you are directed to into its constituent parts. What is each section of the URL doing?  

### Use `nslookup` to find the IP of a website
*This task requires the use of `nslookup` inside your machine's command line interface (CLI).*

Use this to find the IP addresses for Amazon, Google, Facebook and Outlook.

### Use `ping` to query a site using its IP address
*This task requires the use of `ping` inside your machine's CLI.*

Use the IP addresses you gained from the previous task to find the DNS which each of the four sites are using. What do you notice? 

### Disconnect your machine during a `ping` request
*This task requires the use of `ping` inside your machine's CLI.*

Try to `ping` any of the IP addresses from the previous tasks, but either remove your Ethernet cable or deactivate your WiFi during the process. What happens?