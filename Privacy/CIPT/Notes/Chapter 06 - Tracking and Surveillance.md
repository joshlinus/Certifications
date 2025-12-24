#CIPT #IAPP 

## Table of Contents
---
Chapter 6 - Tracking and Surveillance
	*Lorrie Faith Cranor, CIPT; Blase Ur, CIPT*
	[[#Introduction]]
	[[#6.1 Internet Monitoring]]
		[[#6.1.1 Overview of Internet Communications]]
		[[#6.1.2 Network-Scale Monitoring and Deep Packet Inspection]]
		[[#6.1.3 Wi-Fi Eavesdropping]]
		[[#6.1.4 Internet Monitoring for Employers, Schools, and Parents]]
		[[#6.1.5 Spyware]]
		[[#6.1.6 Preventing Network-Level Surveillance]]
	[[#6.2 Web Tracking]]
		[[#6.2.1 Web Tracking Using HTTP Cookies]]
		[[#6.2.2 Web Tracking Using Other Storage Media]]
		[[#6.2.3 Browser Fingerprinting]]
		[[#6.2.4 Google’s FLoC and Topics API Proposals]]
		[[#6.2.5 Cross-Device Tracking]]
		[[#6.2.6 Tracking Email Recipients]]
	[[#6.3 Blocking and Controlling Web Tracking]]
		[[#6.3.1.1 Privacy Settings in Browsers and Do Not Track]]
		[[#6.3.1.2 Web-Based Privacy Tools]]
		[[#6.3.1.2 Web-Based Privacy Tools]]
		[[#6.3.1.4 Deciding What to Block]]
		[[#6.3.3 Blocking Email Tracking]]
	[[#6.4 Location Tracking]]
		[[#6.4.1 Location-Tracking Technologies]]
		[[#6.4.2 Location-Based Services]]
		[[#6.4.4 Preventing and Controlling Location Tracking]]
	[[#6.5 Audio and Video Surveillance]]




## Introduction
---
**Reasons for Tracking:** Tracking is done for various reasons, including:
    - **Commercial:** Advertising companies profiling users for better ad targeting (e.g., the Target example).
    - **Malicious:** Individuals or groups spying for blackmail, extortion, or embarrassment.
    - **Governmental/Organizational:** Gathering intelligence (e.g., thwarting terrorism) or for more insidious purposes.

**Major Revelations:**
    - **PRISM (2013):** Disclosures revealed U.S. and U.K. intelligence agencies partnered with major internet companies to access customer communications, overseen by a secret court.
    - **Cambridge Analytica (2018):** Used data from 50 million Facebook users to identify personalities and influence the 2016 election.
    - **Pegasus Spyware (2021):** Revealed governments' use of surveillance software to track activists and dissidents.



## 6.1 Internet Monitoring
---
###### 6.1.1 Overview of Internet Communications
When data is sent across the internet, it is segmented and encapsulated into **packets** using protocols like Internet Protocol (IP). These packets contain the source and destination IP addresses, along with routing and protocol information.

**Packets**
	• **IP Addresses:** These are numerical identifiers temporarily assigned to connected devices. IPv4 (32 bits) is transitioning to the much larger IPv6 (128 bits).
		• An IP packet is composed of two main parts: a **header** and a **data payload**. The header contains the crucial metadata needed for routing, including:
			• The source and destination IP addresses.
			• Routing and protocol information.
			• A checksum used for error checking.
	• **Transmission Control Protocol (TCP):** Guarantees reliable data delivery and is used when reliability is critical, such as downloading a photo.
	• **User Datagram Protocol (UDP):** Operates faster than TCP but offers no delivery guarantees; used for services like live video streaming.

**Email**
	• Email messages are created using a Mail User Agent (MUA) and sent between servers using the Simple Mail Transfer Protocol (SMTP).
	• The Internet Message Access Protocol (IMAP) generally leaves emails on the server, while Post Office Protocol (POP) typically removes them after local storage.

**Hypertext Transfer Protocols (HTTP/HTTPS)**
	• The Uniform Resource Locator (URL) specifies the service (protocol), host (server), and resource (content).
	• **HTTP** is the primary protocol, but messages are sent in plaintext and are vulnerable to monitoring.
	• **HTTPS** uses Transport Layer Security (TLS) to encrypt the data, offering protection from monitoring and tampering.
	• Requests (like GET or POST) and responses include headers containing additional data about the transaction and the user's browser.

**HTTP Requests: GET vs. POST**
The primary protocols for web communication, Hypertext Transfer Protocol (HTTP) and Secure (HTTPS), utilize distinct request types, primarily GET and POST.

| Request Type | Purpose and Function                                                                                                                                                                  |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **GET**      | Simply requests a specific resource (like a web page or image) to be returned from the server. GET requests can carry data by embedding **query parameters** directly within the URL. |
| **POST**     | Used to send data from the client (browser) to the server. This data is transmitted within the **body** of the POST request, often used for submitting online forms.                  |

Both GET and POST requests transmit **headers** containing additional data. These request headers include the command (GET or POST), the resource requested, the date and time, and identifying information for the user's browser and operating system. A critical piece of information found here is the **referer** header, which tells the destination site the URL of the page the user clicked from.

###### 6.1.2 Network-Scale Monitoring and Deep Packet Inspection
**Deep Packet Inspection (DPI)** involves network equipment examining information beyond the standard IP header, often looking at headers for other protocols or the entire body of the packet.

**Purposes of DPI:**
• **Security:** DPI can be used to scan packets for malicious content, such as known viruses, or to prevent data leaks by detecting sensitive information leaving an organizational network.
• **Surveillance and Tracking:** Advertisers use DPI to track users' online behavior for targeted advertising. Governments, like China's "Great Firewall," use it for large-scale censorship or to track citizens’ activities, which raises significant privacy concerns.
• **Net Neutrality Issues:** DPI can be controversial because it allows for network traffic control based on content. For instance, a provider might use DPI to "rate-limit" or slow down peer-to-peer connections.

###### 6.1.3 Wi-Fi Eavesdropping
Wi-Fi eavesdropping involves network equipment examining data at the packet level on a wireless network. Tools for this, such as packet sniffers like Wireshark, capture and reassemble packet content.

**Vulnerabilities and Attacks:**
	• **Unsecured Networks:** Communications sent over open or shared Wi-Fi (like public hotspots) can be easily intercepted and read if unencrypted.
	• **Session Hijacking (Side-jacking):** Specialized tools, like the former Firesheep extension, intercepted unencrypted authentication tokens sent over Wi-Fi after a user logged in. This allowed an adversary to impersonate the legitimate user. This type of attack drove many websites to adopt HTTPS for all traffic.
	• **Data Misuse:** Even if not intentionally malicious, collected data can be misused. Google's Street View cars captured data, including passwords and personal information, from unencrypted Wi-Fi networks, leading to privacy violation settlements.

**Defenses:**
	• **Encryption:** Wi-Fi networks should be encrypted using WPA2 or WPA3, as older protocols like Wired Equivalent Privacy (WEP) and WPA are insecure.
	• **VPNs:** Virtual private networks (VPNs) create secure, encrypted tunnels for data traveling across untrusted networks.
	• **HTTPS:** Encrypting web requests using HTTPS provides protection regardless of the security level of the local Wi-Fi network.

###### 6.1.4 Internet Monitoring for Employers, Schools, and Parents
Monitoring local networks is common for entities in positions of authority to enforce policies and ensure security.

**Employers**
	• In the United States, employers are legally allowed to monitor employees' internet usage when on the company network or using company-owned machines.
	• Monitoring is used to track productivity, maintain network security, and ensure appropriate employee behavior.
	• Some organizations perform a Machine-in-the-Middle (MiTM) attack by installing themselves as a Certificate Authority (CA) on company machines, which allows them to intercept and decrypt SSL and TLS traffic to read communications.

**Schools**
	• The U.S. Children’s Internet Protection Act (CIPA) mandates that schools and public libraries receiving federal funding must install filters to prevent children from viewing inappropriate content online.
	• Many schools track students' internet usage to prevent inappropriate activities, such as illegal downloading.

**Parents**
	• Parents use various tools to monitor their children's internet usage and online activity.
	• These tools typically allow parents to limit the types of sites their children can visit using blacklists or keyword filters.
	• Tools also enable parents to track visited sites and view emails and chat messages to protect children from online predators and supervise their online behavior

###### 6.1.5 Spyware
**Spyware** is malicious software covertly installed on a user's computer, often by tricking the user through social engineering attacks. Its primary goal is to monitor user activity directly on the device.

**Function and Mechanism:**
	• Spyware commonly operates by performing screen capture or **keylogging**.
	• **Keylogging** records a user's keystrokes, allowing attackers to capture sensitive information such as passwords.

**Installation and Sophistication:**
	• Distribution methods range widely, from simple app downloads (often leveraged in cases of intimate partner violence) to highly sophisticated attacks.
	• Advanced attackers may use complex **spear-phishing** techniques or exploit previously unreported **zero-click vulnerabilities** in software to install spyware (e.g., Pegasus).

**Defenses:**
	• Antispyware programs use antimalware signatures to detect and remove known spyware.
	• However, these detection systems are generally **reactive** and may fail to identify and remove newer, unknown forms of spyware

###### 6.1.6 Preventing Network-Level Surveillance
Even when data is encrypted using HTTPS, it is often still possible for observers like ISPs or governments to learn which sites a user accesses by examining **metadata**. This occurs because network observers can still view the source and destination IP addresses, as well as other data left unencrypted in the packet headers for routing purposes. Consequently, HTTPS alone does not provide anonymity.

To counter this tracking, **anonymizers** are employed to mask the link between the data source (the user) and the traffic destination.
	• **Anonymous Proxies:** These systems route the user’s network traffic through an intermediary, making the traffic appear to originate from the proxy server’s IP address.
	• **Onion-Routing Systems (Mix Networks):** These systems encrypt packets in multiple layers and send them through a series of relays, making the traffic extremely difficult to trace. **Tor** is a common implementation of this protocol.
Beyond technical surveillance, users must also worry about the disclosure of personal data to governments or other organizations through the cooperation of internet companies, often without the user’s knowledge. For instance, despite promises that Skype could not intercept communications, revelations from the PRISM program showed this was false


## 6.2 Web Tracking
---
###### 6.2.1 Web Tracking Using HTTP Cookies
HТP cookies are small text files that websites request a web browser save to maintain state because web protocols like HТP are inherently stateless,.

**Mechanism and Types**
	• **Creation:** A server uses the "set-cookie" header in an HТP response to request storage. The cookie contains values, an expiration date, and defines its scope (domain and path).
	• **Retrieval:** When a user returns, the browser automatically includes the cookie contents in the HТP request header, enabling the site to identify the user via a unique identifier,.
	• **Session Cookies** last only until the browser is closed.
	• **Persistent Cookies** are saved indefinitely and used to correlate visits over long periods.
	**First-Party vs. Third-Party Tracking**
	• **First-Party Cookies** are set by the primary website a user visits.
	• **Third-Party Cookies** are set by domains other than the primary website, such as those hosting images, advertisements, or web bugs (beacons).

**Third-Party Tracking and Behavioral Advertising**
Third-party cookies are set by domains that differ from the primary website the user is visiting, such as domains hosting advertisements or web bugs. When a user’s browser requests this third-party content (like a tracking pixel or ad), the request automatically includes the unique cookie assigned by that third party, as well as the **referer** header. The referer header reveals the URL of the original page the user was visiting. By correlating the unique user ID in the cookie with the list of URLs received via the referer header across many sites, third parties can build detailed user profiles. This profiling forms the basis for **online behavioral advertising**.

**Cookie Syncing Mechanism**
Cookie syncing is a technique used by different companies to match and merge the unique pseudonymous identifiers they have independently assigned to the same user. This process is necessary because the **same-origin policy** prevents one company (e.g., Company A) from directly reading the cookies set by another company (e.g., Company B).

The mechanism works by initiating a specialized, indirect communication:
	1. Company A reads its own user identifier from its cookie (e.g., ID "123").
	2. Company A embeds this ID into an HTTP request sent directly to Company B's domain, usually placing it within the URL parameters.
	3. When the browser sends this request to Company B's domain, the browser automatically includes Company B's own cookie identifier for the user (e.g., ID "789") in the request header.
	4. Company B receives the request and correlates ID "123" (from the URL) with ID "789" (from the cookie), successfully creating a synchronized mapping of the user across both tracking systems.

**Other Tracking Methods**
	• **URL Rewriting** allows websites to track which link a user clicks by rerouting the request through the site's own server before redirecting the user to the final destination,.
	• **Social Widgets**, like a Facebook "Like" button, enable social media companies to notice a user's visit to a page, regardless of whether the user interacts with the widget

###### 6.2.2 Web Tracking Using Other Storage Media
Web tracking often relies on storage mechanisms beyond standard HTTP cookies, frequently misusing features intended for performance or functionality to store unique user identifiers.

**Local Shared Objects (LSOs) / Flash Cookies**
	• **Mechanism:** Adobe Flash Player used Local Shared Objects (LSOs), often called "Flash cookies," to store information separately from standard HTTP cookies.
	• **Persistence:** LSOs were initially problematic because clearing web browser cookies did not automatically remove them.
	• **Respawning:** Tracking companies exploited this separation by using identifiers stored in LSOs to "respawn" deleted HTTP cookies with the same unique identifier, undermining user attempts to clear tracking data,. This practice persisted for years, often in violation of user expectations.

**Other Storage Methods**
	• **HTML5 / DOM Storage:** The HTML5 markup language and related Document Object Model (DOM) storage methods introduced new ways for browsers to store data locally.
	    ◦ **Session Storage:** Saves information only for the current browser window and is cleared when the window is closed.
	    ◦ **Local Storage:** Stores data semi-permanently, making it available to the domain that set the data across future sessions.
	• **ETags:** Entity tags (ETags) are HTTP headers originally intended to enhance performance by tagging resources (like images) so the browser knows when to reload them. However, web servers can use ETags to assign a unique identifier to a user that persists even when HTTP cookies are deleted, as ETags are removed only when the browser cache is cleared.
	• **Legacy/Hacks:** Other mechanisms include Silverlight isolated storage, JavaScript's `window.name` property, Internet Explorer's `userData` storage, and the "pixel hack," where unique identifiers are embedded into minuscule cached images,.
	• **Evercookie:** The "Evercookie" was a prototype combining many of these resilient storage techniques (like LSOs and ETags) to make identifying data extremely difficult for users to delete

###### 6.2.3 Browser Fingerprinting
**Browser fingerprinting** is a technique used by websites to create a unique, stable identifier for a user, even if they have disabled or deleted cookies. This method misuses features designed to enhance the user experience to collect specific configuration attributes.

**Mechanism and Scope:**
	• Websites use JavaScript functions to collect detailed configuration data from the user’s device. This data typically includes the operating system and its version, the browser version, screen resolution, time zone, installed fonts, and plug-ins.
	• When combined, these idiosyncratic characteristics create a fairly unique profile of the user. Studies have shown that a high percentage (e.g., 94.2% in one 2010 study for browsers with Flash or Java) of configurations can be uniquely identified.
	• This unique configuration acts as a semi-stable identifier, substituting the person's real identity, which constitutes **pseudonymity**. Because the identifier is often sent in the HTTP request header, fingerprinting became a major frontier in online tracking even as cookie blocking increased.

**Mitigation:**
	• A user can attempt to mitigate this by configuring web server logs to record less information from the HTTP request header.
	• There is an ongoing "arms race" between those who develop new fingerprinting techniques and those who create defenses to block them.

###### 6.2.4 Google’s FLoC and Topics API Proposals
Google introduced and tested the **Federated Learning of Cohorts (FLoC)** starting in 2021 as an approach to enable targeted advertising while avoiding reliance on third-party cookies. FLoC was designed to assign a user to a "cohort" (a group containing thousands of users) based on the sites they visited, with this processing taking place directly on the user's device rather than on a central server.

FLoC was criticized as potentially being "privacy theater" because the cohort ID could make the user’s browser easier to fingerprint and allowed organizations where users logged in to link the ID back to personal data. Furthermore, cohorts risked overrepresenting specific demographic groups, which could facilitate discrimination.

In 2022, Google abandoned FLoC and introduced the **Topics API** as a replacement. The Topics API still profiles the user in the browser but assigns them to five interest categories (starting with approximately 350 categories) instead of a single cohort ID. Despite this change, privacy advocates remain concerned that the Topics API allows Google to determine where tracking occurs and still enables widespread targeted advertising.

###### 6.2.5 Cross-Device Tracking
Cross-device tracking involves monitoring a user across multiple devices, such as computers, smartphones, and smart TVs. While this is useful for functions like maintaining session state or resuming content on a different screen, companies often use it to build rich user profiles for advertising and other purposes.

**Tracking Methods:**
	• **Deterministic:** This approach is used when a user logs into a service on each device, allowing companies to confirm the identity of the user across platforms.
	• **Probabilistic:** If a user is not logged in, companies use indirect data like matching IP addresses, cookies, location, and behavioral data to probabilistically infer that the devices belong to the same person.

###### 6.2.6 Tracking Email Recipients
Tracking whether an email has been opened or if links within it have been clicked uses techniques similar to web tracking, primarily variants of beacons and URL rewriting.

**Tracking Mechanism**
	• **Beacons (Image Tracking):** Popular email programs often display HTML content, which allows emails to request external content like images. To track if an email is opened, the HTML code requests content from a unique URL on a remote server (often a zero- or one-pixel image). If the server receives a request for that unique URL, the sender knows the recipient opened the email and the exact time it occurred.
	• **URL Rewriting:** Links embedded in an email may be customized with unique identity


## 6.3 Blocking and Controlling Web Tracking
---
###### 6.3.1.1 Privacy Settings in Browsers and Do Not Track
Browser settings provide a primary method for users to block or limit web tracking, mainly by controlling HТP cookies,. This process often involves navigating a tension between privacy and functionality, as blocking third-party cookies can sometimes break website functions.

**Core Browser Features:**
Browsers increasingly differentiate themselves by their default privacy postures.
	• **Default Blocking:** Apple Safari and Mozilla Firefox block known third-party cookies by default. Firefox determines which third-party cookies to block using lists of known trackers, such as those curated by Disconnect.
	• **Advanced Protection:** Features like Firefox's Enhanced Tracking Protection (ETP) and Safari's Intelligent Tracking Protection (ITP) limit major tracking vectors by relying on blocklists or setting time limits on cookie retention.
	• **Fingerprinting Defense:** Privacy-focused browsers, like Brave, also use heuristics to detect and block attempts at browser fingerprinting, which is a method trackers use to create unique identifiers even without cookies.

**Private Browsing Modes**
All major browsers offer private modes (e.g., Incognito or Private Browsing) that prevent the local storage of browsing history and cookies accumulated during that session. However, these modes provide only minimal protection from external tracking and surveillance, and users often hold inaccurate expectations about the true level of privacy offered.

**The Failure of Do Not Track (DNT)**
The Do Not Track (DNT) feature was an HTTP header designed to communicate a user's preference _not_ to be tracked. It failed largely because it relied on websites voluntarily honoring the request, rather than technically blocking the tracking. Prolonged debates within standards bodies over the precise meaning of the DNT signal, combined with widespread lack of voluntary compliance from websites, led to the system being largely abandoned

**Platform for Privacy Preferences Project (P3P) Tokens**
The Platform for Privacy Preferences Project (P3P) was a World Wide Web Consortium (W3C) standard that used a machine-readable language to allow websites to express their privacy practices, such as the information they collect and how it is used.
	• **Functionality:** P3P tokens were used by older versions of the Internet Explorer browser (IE 6 through 10) to make decisions about cookies. IE would block third-party cookies if they did not have a P3P token or if their P3P token indicated a privacy policy considered unsatisfactory by Microsoft's criteria. This allowed cookie decisions to be made based on how the cookies would be used.
	• **Drawbacks and Failure:** Despite being a W3C standard, IE was the only major web browser that utilized P3P, and adoption by websites was low. Furthermore, some sites intentionally misrepresented their privacy policies by using nonsensical or sample P3P tokens to bypass IE's blocking mechanism, rendering the system unreliable.

###### 6.3.1.2 Web-Based Privacy Tools
Users can utilize web-based tools and interfaces provided by tracking companies or industry groups to control or learn about web tracking. However, these tools often provide limited utility:

**Ad Preference Dashboards**
	• Companies like Google and Facebook provide dashboards where users can view and sometimes edit the inferred profiles of their interests, often for targeted advertising purposes.
	• A key drawback is that these dashboards generally provide an incomplete and sometimes misleading view of the raw data collected about the user.

**Ad Explanations and Icons**
	• Some companies offer explanations about why a user received a specific advertisement, but these explanations are frequently incomplete or factually inaccurate.
	• The standardized AdChoices icon, intended to inform consumers about targeted ads and provide opt-out links, has historically been found to poorly communicate its purpose and choices to users.

**Cookie Notices and Opt-Outs**
	• Regulations, such as those in the EU, mandate conspicuous notices about cookie use and require explicit opt-in consent for tracking. Despite this, websites sometimes set cookies before consent is given.
	• Some companies offer **opt-out cookies**, which signal the user's preference not to receive targeted ads. However, these cookies are often deleted when a user clears their browser cookies, undermining the opt-out preference. Furthermore, users who use opt-out cookies may still be tracked by the company.
	• Centralized websites exist to allow a user to opt out of tracking from many companies at once, but these also often suffer from significant usability problems

###### 6.3.1.4 Deciding What to Block
The decision of what to block is a central dilemma in web tracking defenses, as blocking too little is ineffective, but blocking too much can break website functionality. Users often struggle with this decision due to the inherent complexity of tracking technologies and major misconceptions about how they work.

Strategies used to manage this dilemma include:
	• **Precompiled Lists** Organizations or experts create blacklists and whitelists of domains to block (e.g., used by Adblock Plus or Internet Explorer’s Tracking Protection Lists). While these lists simplify the process, they may not precisely match an individual user's complex privacy preferences.
	• **Algorithmic Blocking** Tools like the EFF's Privacy Badger use heuristics and algorithmic methods to automatically identify and block potential tracking mechanisms.
	• **Functional Privacy** Users often seek "functional privacy"—the greatest amount of privacy they can get without breaking the ability of a website to work correctly. To achieve this, some users adopt overriding strategies, such as using different browsers for different activities or employing privacy-preserving proxies that strip identifying information

###### 6.3.3 Blocking Email Tracking
Discusses how modern email clients can help block tracking, primarily by controlling external content:

**Key Details on Blocking Email Tracking:**
	• Tracking in emails uses beacons (image tracking) and URL rewriting.
	• Email clients that block external content (like images and beacons) by default disable one of the most widespread tracking methods used to determine if a message has been opened.
	• This defense is incomplete because tracking can still occur through **URL rewriting** if a user clicks on customized links within the email.
	• Privacy-conscious users should avoid following links in emails to prevent tracking and phishing.
	• Users sometimes turn off the default image-blocking feature, often because they are unaware of its privacy benefits since email clients rarely explain the reasons for blocking external resources.
	• Some mail servers, such as Gmail, help mitigate risks by serving all external images through their own proxy, which prevents trackers from learning the recipient's IP address (location) when the message is opened.


## 6.4 Location Tracking
---
###### 6.4.1 Location-Tracking Technologies
**6.4.1.1 Wi-Fi and Cell Tower Triangulation**
Location can be determined using cellular and Wi-Fi signals. A device's position is calculated geometrically through triangulation based on the timing and strength of signals relative to known cell tower locations. Wi-Fi signals offer more fine-grained location data due to their shorter range, while cell towers provide less granular, but more permanent, location markers. This tracking is most effective in urban areas with a high density of access points.

**6.4.1.2 GPS**
Global Positioning System (GPS) satellites determine a device's longitude, latitude, and altitude. A GPS receiver calculates its position by receiving signals from at least four geosynchronous satellites. Using GPS itself does not automatically reveal a device's location, as it only receives signals and does not transmit them. However, GPS-enabled devices, such as smartphones, can subsequently share this location information with apps or providers.

**6.4.1.3 RFIDs**
Radio Frequency Identification (RFID) chips transmit a unique serial number via an antenna to an RFID reader. Passive chips transmit when powered by a reader, while active chips have their own power source for a longer range. Tracking occurs as readers pick up the unique tag IDs at various locations.

**6.4.1.4 Phone Tracking**
A mobile phone's location can be tracked by receivers in building complexes. In the U.S., the FCC requires phone companies to track phones when an emergency 911 call is placed. Some services, such as a "mobile phone survey" tested by shopping malls, have tracked shoppers' locations via their cell phones, requiring customers to turn their devices off to opt out.

**6.4.1.5 Bluetooth-Based Tracking Tags**
Devices like Apple AirTags use Bluetooth to connect to nearby compatible Apple devices with the "find my" feature enabled. The connected device sends the tag's location back to the owner (via an encrypted process). However, these devices have been used for stalking, leading companies to develop new techniques to alert users if an unknown tag is consistently nearby.

**6.4.1.6 Metadata**
Location can be automatically stored in the metadata of content like photos taken with GPS-enabled devices (e.g., cell phones or cameras), sometimes without the user's awareness.

###### 6.4.2 Location-Based Services
Location-based services utilize data from tracking technologies to augment various systems, including social media and apps, and enable new uses like individual tracking and location-based advertising.

**6.4.2.1 Social Media**
Apps like Foursquare allow users to "check in" at locations and view friends' check-ins, often motivated by earning badges or coupons. Other social media platforms, such as Facebook Places, also augment their services by allowing users to check in at locations.

**6.4.2.2 Location-Based Apps**
Location data supports numerous applications, including maps and directions, local weather updates, and finding nearby services or items. Mobile mapping apps typically determine a user's location using a combination of GPS, Wi-Fi, and cell tower triangulation. Furthermore, location-based apps can help device owners locate a lost or stolen smartphone or similar device. However, carelessly assigning geographic metadata (geotagging) to content, such as photos, can create security and privacy risks, potentially leaking precise addresses or alerting criminals when a person is away from home.

**6.4.2.3 Tracking Children and Employees**
Location-based services are commonly used by parents to track their children's cell phones via parental control apps. Employers may also use GPS trackers or RFID chips to monitor employee locations for efficiency, security, or liability reasons. The shift to work-from-home arrangements increased employee tracking via tools that log keystrokes, take screenshots, and monitor web use.

**6.4.2.4 Location-Based Ads**
Advertisers utilize location data to offer targeted advertising, often using a "geofence" to identify when a consumer is near a targeted location. Consumers frequently have significant privacy concerns about sharing location information with advertisers, although providing user controls (e.g., restricting sharing by time) can mitigate some of these concerns.

**6.4.2.5 Combining with Data from Other Sources**
Location data can be combined with data from other sources to enable inferences that wouldn't be possible from each source alone. For example, combining check-in data from Foursquare and Twitter allowed the Please Rob Me website to identify users likely away from home. Similarly, the Girls Around Me app used location and gender data from Foursquare to enable searching for nearby women, leading Foursquare to cut off the app's access to its data.

###### 6.4.4 Preventing and Controlling Location Tracking
Location tracking is difficult to block entirely, as triangulation techniques can sometimes track a mobile phone's location even when the device is turned off but the battery remains connected. However, systems are being developed to allow more granular control over location sharing.

**6.4.4.1 Blocking Tracking**
Users can limit or block tracking based on the type of technology involved.
	• **Service Opt-Outs:** For location-based apps, a user can opt out of location tracking, or remove location data from content after it has been added. Smartphone apps typically require the user to decide whether to enable location tracking upon download.
	• **Metadata:** Location metadata can be removed from content, such as deleting location data from photos using editing apps.
	• **RFID Chips:** Tracking via RFID chips can be physically blocked by placing a protective sleeve over the item, or the chip can be physically removed.

**6.4.4.2 User Controls**
Since completely blocking location data is often undesirable because it limits service functionality, controlling _who_ has access to the data is an alternative.
	• **Granularity and Context:** Location-based services allow users to set privacy settings with different levels of granularity. For instance, location-sharing preferences often vary based on the time of day, the group being shared with, or the location itself.
	• **Awareness:** A critical first step in promoting user control is making them aware that their location is being shared, as Apple and Google attempted to do regarding AirTags. Quantifying leaks of location information can also prompt users toward more privacy-protective behaviors.

**6.4.4.3 Research into Privacy Protections for Location**
Providing the benefits of location sharing while preserving user privacy remains a challenge.
	• **Deidentification:** Completely deidentifying an individual's location trace is difficult because permanent patterns, such as home and workplace location, can uniquely identify many people.
	• **Proximity Detection:** Researchers have prototyped systems that use location tags to detect whether two users of a location-based service are near each other, without revealing either user’s exact location.


## 6.5 Audio and Video Surveillance
---
This section covers how audio and video devices, both consumer electronics and purpose-built systems, enable widespread surveillance.

###### 6.5.1 Hidden Cameras and Microphones
Hidden cameras and microphones are used for surveillance and can be purpose-built, disguised (like "nanny cams"), or repurposed consumer devices.
	• **Smartphones:** They contain microphones and cameras that can be remotely activated, essentially functioning as "roving bugs" via malware,. Domestic abusers use apps to spy on victims. Historically, the FBI has used such remote audio surveillance under the U.S. Wiretap Act.
	• **Laptops and Desktops:** These devices are vulnerable to audio and video surveillance, often via malware like Remote Access Trojans (Tots). Monitoring by employers or schools (such as unauthorized webcam use) has led to legal issues.
	• **Smart Televisions:** Many modern smart TVs include microphones for voice control and continuously transmit recorded audio to remote servers for processing. They also use Automated Content Recognition (ACR) to track viewing habits. Malware, such as the CIA's "Weeping Angel" program, can keep the microphone active even when the television appears to be off.
	• **Drones (UAVs):** Low-cost consumer drones are used for recreation, photography, and surveillance, and can include video cameras, infrared, and radar sensors,.

###### 6.5.2 CCTV
Closed-circuit television (CCTV) systems are widely deployed, with analysts estimating over one billion cameras installed worldwide as of 2021,. These systems transfer images to a remote destination for real-time or post-hoc monitoring by law enforcement or security personnel. Their use has become a prominent privacy issue due to the rapidly increasing camera density and advances in facial recognition technology.

###### 6.5.3 Facial Recognition
Facial recognition enables large-scale tracking by processing images from public cameras.
	• The technology is used by governments, notably in China, for applications ranging from identifying jaywalkers to tracking ethnic minority groups,.
	• Companies like Clearview AI trained facial recognition algorithms on billions of images scraped from the internet, often without permission. The potential for widespread tracking has led to bans in some cities, although some of these bans are now being lifted.

###### 6.5.4 Video Doorbells and Citizen Surveillance
The widespread adoption of internet-connected video doorbells, like Amazon Ring, has created a system of civilian mass surveillance.
	• These devices typically record video and audio when activated by motion or a doorbell press.
	• Manufacturers sometimes share the collected data with police departments, enabling widespread warrantless surveillance.
	• These devices also collect information on how users interact with the video data and characteristics of their home network.

###### 6.5.5 Tracking Voice over IP Conversations
VoIP communications (like Skype) can be tracked due to vulnerabilities that unintentionally enable eavesdropping, or intentionally tracked due to legal requirements such as the Communications Assistance for Law Enforcement Act (CALEA),. Even if the conversation content is encrypted, metadata about the communication can reveal a large amount of information.

###### 6.5.6 Speech Recognition
Smart speakers and voice assistants (like Alexa and Google Home) are ubiquitous, putting microphones in users' personal spaces.
	• Speech recognition processing is often performed on remote servers, meaning incidental conversations are continually recorded and transmitted.
	• Controversy arose when it was revealed that human employees were listening to and manually annotating recordings to improve speech recognition algorithms.

###### 6.5.7 Audio and Video Surveillance in Educational Technology
Technology in educational settings is a growing source of surveillance, especially since the COVID-19 pandemic increased the use of remote tools.
	• Students, who are vulnerable individuals, are tracked through detailed analytics on attendance and attention.
	• Remote proctoring services for high-stakes tests monitor test-takers' screens and environments, leading to controversy and a ruling by a federal judge that virtual room scans are unconstitutional.

###### 6.5.8 Protecting against Audio and Video Surveillance
Protection requires layered defenses:
	• **Malware Protection:** Use antivirus software to prevent malware from taking over a device's camera or microphone.
	• **Physical Blocking:** Low-tech solutions like covering the camera when not in use are highly effective. Indicator lights on cameras provide awareness, but sophisticated malware can sometimes evade them.
	• **Microphones:** Solutions for disabling microphones are difficult; effective, inexpensive microphone jammers are not yet widely available.
	• **Network:** Tracking and blocking suspicious network traffic can help prevent surveillance.


## **6.6 Sensor-Based Surveillance**
---
The widespread deployment of sensors in modern technology—from smartphones to Internet of Things (IoT) devices—has made constant surveillance possible, leading to potential tracking and leakage of private information.

**Ubiquitous Computing and Emerging Technologies**
	• **Smart Cities:** These systems aggregate vast amounts of data and deploy sensors for purposes such as noise or energy monitoring. This enables large-scale surveillance of citizens, raising concerns about policing and chilling effects on the right to dissent. For instance, smart meters can infer household activity, like TV viewing habits, from granular power consumption data,.
	• **Augmented Reality (AR):** AR systems, which require rich sensor data to overlay virtual content onto the real world, create privacy tensions. Users have raised concerns about how observations from AR applications might invade their physical privacy.

**Mobile Devices and IoT**
	• **Mobile Device Sensors:** Smartphones are inherently "surveillance devices" due to sensors like accelerometers, which measure speed and can reveal information about distance traveled or even passwords typed,. Biometric data like fingerprints, often used for authentication, are unique identifiers that are impossible to replace.
	• **Internet of Things (IoT):** The lack of traditional user interfaces on IoT devices (such as internet-connected toys or smart home security systems) makes providing privacy notices and controls difficult,,. Well-intentioned uses, like eldercare technology, can still cause the person under care to feel a loss of control and surveillance.
	• **Home Automation:** Systems like smart thermostats and lighting funnel sensor data through cloud interfaces, making the traditionally private home a trackable space. This can allow companies like Amazon and Google to track and surveil what happens inside consumers' homes.

**Connected Vehicles and Wearables**
	• **Vehicle Sensors:** Modern cars are complex networks of computers and sensors that record data on speed, braking, and other characteristics. This data, sometimes stored in "black boxes," is subject to access questions by law enforcement, insurance, and advertisers. External tools like Automated License Plate Readers (ALPRs) also contribute to tracking vehicle movements.
	• **Wearable Devices:** Fitness trackers often send detailed data to centralized repositories. This data, not typically protected as health data, can inadvertently leak sensitive information, such as military base outlines found through public Strava fitness routes.
	• **The Metaverse:** Virtual and augmented reality environments, like the Metaverse, promise all-encompassing sensing using headsets and full-body trackers. This can lead to new tracking challenges, including the monitoring of a user's gaze and attention to infer psychological states