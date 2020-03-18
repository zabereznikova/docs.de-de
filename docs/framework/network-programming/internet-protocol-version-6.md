---
title: Internetprotokoll Version 6
ms.date: 03/30/2017
helpviewer_keywords:
- IPv6, improvements
- IPv4
- IPv6
- Internet Protocol version 6, improvements
- Internet Protocol version 6
ms.assetid: e6fa8ebd-010a-4c48-a5ec-a5102c53c06f
ms.openlocfilehash: 367db4fa4e585d6066009dbd1afacb154829319a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047878"
---
# <a name="internet-protocol-version-6"></a><span data-ttu-id="8d348-102">Internetprotokoll Version 6</span><span class="sxs-lookup"><span data-stu-id="8d348-102">Internet Protocol Version 6</span></span>
<span data-ttu-id="8d348-103">Das Internetprotokoll Version 6 (IPv6) ist eine neue Standardprotokollsammlung für die Netzwerkebene des Internets.</span><span class="sxs-lookup"><span data-stu-id="8d348-103">The Internet Protocol version 6 (IPv6) is a new suite of standard protocols for the network layer of the Internet.</span></span> <span data-ttu-id="8d348-104">IPv6 wurde entwickelt, um viele Probleme der aktuellen Version der Internetprotokollsammlung (IPv4) hinsichtlich Adressenknappheit, Sicherheit, automatischer Konfiguration, Bedarf an Erweiterbarkeit usw., zu lösen.</span><span class="sxs-lookup"><span data-stu-id="8d348-104">IPv6 is designed to solve many of the problems of the current version of the Internet Protocol suite (known as IPv4) with regard to address depletion, security, auto-configuration, extensibility, and so on.</span></span> <span data-ttu-id="8d348-105">IPv6 erweitert die Funktionen des Internets, um neue Arten von Anwendungen zu ermöglichen, einschließlich Peer-zu-Peer-Anwendungen und mobile Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="8d348-105">IPv6 expands the capabilities of the Internet to enable new kinds of applications, including peer-to-peer and mobile applications.</span></span> <span data-ttu-id="8d348-106">Nachfolgend sind die Hauptprobleme des aktuellen IPv4-Protokolls aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="8d348-106">The following are the main issues of the current IPv4 protocol:</span></span>  
  
- <span data-ttu-id="8d348-107">Schnelle Erschöpfung des Adressraums</span><span class="sxs-lookup"><span data-stu-id="8d348-107">Rapid depletion of the address space.</span></span>  
  
     <span data-ttu-id="8d348-108">Dies hat zur Verwendung von Netzwerkadressübersetzungen (NATs, Network Address Translators) geführt, wodurch mehrere private Adressen einer einzelnen IP-Adresse zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="8d348-108">This has led to the use of Network Address Translators (NATs) that map multiple private addresses to a single public IP address.</span></span> <span data-ttu-id="8d348-109">Die wichtigsten dadurch entstandenen Probleme sind Mehraufwand und Verlust von End-to-End-Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="8d348-109">The main problems created by this mechanism are processing overhead and lack of end-to-end connectivity.</span></span>  
  
- <span data-ttu-id="8d348-110">Fehlende hierarchische Unterstützung</span><span class="sxs-lookup"><span data-stu-id="8d348-110">Lack of hierarchy support.</span></span>  
  
     <span data-ttu-id="8d348-111">Aufgrund seiner inhärenten Organisation in vordefinierte Klassen verfügt IPv4 über keine echte hierarchische Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="8d348-111">Because of its inherent predefined class organization, IPv4 lacks true hierarchical support.</span></span> <span data-ttu-id="8d348-112">Die IP-Adressen können unmöglich so strukturiert werden, dass sie der tatsächlichen Netzwerktopologie entsprechen.</span><span class="sxs-lookup"><span data-stu-id="8d348-112">It is impossible to structure the IP addresses in a way that truly maps the network topology.</span></span> <span data-ttu-id="8d348-113">Durch diesen entscheidenden Entwurfsfehler sind umfangreiche Routingtabellen notwendig, um IPv4-Pakete an einem beliebigen Speicherort im Internet bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="8d348-113">This crucial design flaw creates the need for large routing tables to deliver IPv4 packets to any location on the Internet.</span></span>  
  
- <span data-ttu-id="8d348-114">Komplexe Netzwerkkonfiguration</span><span class="sxs-lookup"><span data-stu-id="8d348-114">Complex network configuration.</span></span>  
  
     <span data-ttu-id="8d348-115">Mit IPv4 müssen Adressen statisch oder mithilfe eines Configuration-Protokolls, wie z.B. DHCP, zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="8d348-115">With IPv4, addresses must be assigned statically or using a configuration protocol such as DHCP.</span></span> <span data-ttu-id="8d348-116">Idealerweise sollten Hosts nicht auf die Verwaltung einer DHCP-Infrastruktur vertrauen müssen.</span><span class="sxs-lookup"><span data-stu-id="8d348-116">In an ideal situation, hosts would not have to rely on the administration of a DHCP infrastructure.</span></span> <span data-ttu-id="8d348-117">Sie sollten stattdessen selbst Konfigurationen basierend auf dem Netzwerksegment, in dem sie sich befinden, vornehmen können.</span><span class="sxs-lookup"><span data-stu-id="8d348-117">Instead, they would be able to configure themselves based on the network segment in which they are located.</span></span>  
  
- <span data-ttu-id="8d348-118">Fehlende integrierte Authentifizierung und Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="8d348-118">Lack of built-in authentication and confidentiality.</span></span>  
  
     <span data-ttu-id="8d348-119">IPv4 erfordert keine Unterstützung für jedweden Mechanismus zur Authentifizierung oder Verschlüsselung der ausgetauschten Daten.</span><span class="sxs-lookup"><span data-stu-id="8d348-119">IPv4 does not require the support for any mechanism that provides authentication or encryption of the exchanged data.</span></span> <span data-ttu-id="8d348-120">Dies ändert sich mit IPv6.</span><span class="sxs-lookup"><span data-stu-id="8d348-120">This changes with IPv6.</span></span> <span data-ttu-id="8d348-121">Internetprotokollsicherheit (IPSec, Internet Protocol Security) ist eine Supportanforderung von IPv6.</span><span class="sxs-lookup"><span data-stu-id="8d348-121">Internet Protocol security (IPSec) is an IPv6 support requirement.</span></span>  
  
 <span data-ttu-id="8d348-122">Eine neue Protokollsammlung muss die folgenden grundlegenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="8d348-122">A new protocol suite must satisfy the following basic requirements:</span></span>  
  
- <span data-ttu-id="8d348-123">umfangreiches Routing und Adressierung mit geringem Mehraufwand</span><span class="sxs-lookup"><span data-stu-id="8d348-123">Large-scale routing and addressing with low overhead.</span></span>  
  
- <span data-ttu-id="8d348-124">automatische Konfiguration für verschiedene Verbindungssituationen</span><span class="sxs-lookup"><span data-stu-id="8d348-124">Auto-configuration for various connecting situations.</span></span>  
  
- <span data-ttu-id="8d348-125">integrierte Authentifizierung und Vertraulichkeit</span><span class="sxs-lookup"><span data-stu-id="8d348-125">Built-in authentication and confidentiality.</span></span>  
  
 <span data-ttu-id="8d348-126">Weitere Informationen finden Sie unter [IPv6-Adressierung](ipv6-addressing.md), [IPv6-Routing](ipv6-routing.md), [IPv6 Auto-Configuration (Automatische IPv6-Konfiguration)](ipv6-auto-configuration.md), [Enabling and Disabling IPv6 (Aktivieren und Deaktivieren von IPv6)](enabling-and-disabling-ipv6.md) und [How to: Modify the Computer Configuration File to Enable IPv6 Support (Vorgehensweise: Ändern der Computerkonfigurationsdatei zum Aktivieren der IPv6-Unterstützung)](how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).</span><span class="sxs-lookup"><span data-stu-id="8d348-126">For more information, see [IPv6 Addressing](ipv6-addressing.md), [IPv6 Routing](ipv6-routing.md), [IPv6 Auto-Configuration](ipv6-auto-configuration.md), [Enabling and Disabling IPv6](enabling-and-disabling-ipv6.md), and [How to: Modify the Computer Configuration File to Enable IPv6 Support](how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).</span></span>  
  
## <a name="references"></a><span data-ttu-id="8d348-127">Verweise</span><span class="sxs-lookup"><span data-stu-id="8d348-127">References</span></span>  
 <span data-ttu-id="8d348-128">Nachfolgend finden Sie eine Auswahl von RFC-Dokumenten, die Sie auf der Webseite der [Engineering Task Force (IETF)](https://www.ietf.org/) finden können:</span><span class="sxs-lookup"><span data-stu-id="8d348-128">The following are selected RFC documents that you can find at the [Internet Engineering Task Force (IETF)](https://www.ietf.org/) website:</span></span>  
  
- <span data-ttu-id="8d348-129">RFC 1287: Towards the Future Internet Architecture (Internetarchitektur der Zukunft)</span><span class="sxs-lookup"><span data-stu-id="8d348-129">RFC 1287, Towards the Future Internet Architecture.</span></span>  
  
- <span data-ttu-id="8d348-130">RFC 1454: Comparison of Proposals for Next Version of IP (Vergleich von Vorschlägen für die nächste IP-Version)</span><span class="sxs-lookup"><span data-stu-id="8d348-130">RFC 1454, Comparison of Proposals for Next Version of IP.</span></span>  
  
- <span data-ttu-id="8d348-131">RFC 2373: IP Version 6 Addressing Architecture (Adressierungsarchitektur von IP Version 6)</span><span class="sxs-lookup"><span data-stu-id="8d348-131">RFC 2373, IP Version 6 Addressing Architecture.</span></span>  
  
- <span data-ttu-id="8d348-132">RFC 2374: An IPv6 Aggregatable Global Unicast Address Format (Ein globales aggregierbares Unicast-Adressenformat in IPv6)</span><span class="sxs-lookup"><span data-stu-id="8d348-132">RFC 2374, An IPv6 Aggregatable Global Unicast Address Format.</span></span>  
  
 <span data-ttu-id="8d348-133">Informationen zu IPv6 finden Sie auch in der [IP-Version 6 (IPv6)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd379498%28v=ws.10%29).</span><span class="sxs-lookup"><span data-stu-id="8d348-133">You can also find IPv6-related information on the [IP Version 6 (IPv6)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd379498%28v=ws.10%29).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d348-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8d348-134">See also</span></span>

- [<span data-ttu-id="8d348-135">Beispiel für Socket-IPv6</span><span class="sxs-lookup"><span data-stu-id="8d348-135">IPv6 Sockets Sample</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/ms180981%28v=vs.85%29)
- [<span data-ttu-id="8d348-136">Network Programming Samples (Beispiele zur Netzwerkprogrammierung)</span><span class="sxs-lookup"><span data-stu-id="8d348-136">Network Programming Samples</span></span>](network-programming-samples.md)
- [<span data-ttu-id="8d348-137">Sockets</span><span class="sxs-lookup"><span data-stu-id="8d348-137">Sockets</span></span>](sockets.md)
