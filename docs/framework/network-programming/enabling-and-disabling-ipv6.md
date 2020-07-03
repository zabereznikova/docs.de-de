---
title: Aktivieren und Deaktivieren von IPv6
description: Führen Sie diese Konfigurationsschritte aus, um die Verwendung des IPv6-Protokolls zu aktivieren, einschließlich der Änderung der Konfigurationsdatei für den Computer oder für die Anwendung.
ms.date: 03/30/2017
ms.assetid: 6408d3ef-c9ba-49d9-b15e-fe74bd3ef031
ms.openlocfilehash: 7729647b09df20a98d5d639a641cb0a31f557330
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502612"
---
# <a name="enabling-and-disabling-ipv6"></a><span data-ttu-id="ae832-103">Aktivieren und Deaktivieren von IPv6</span><span class="sxs-lookup"><span data-stu-id="ae832-103">Enabling and Disabling IPv6</span></span>
<span data-ttu-id="ae832-104">Um das IPv6-Protokoll verwenden zu können, stellen Sie sicher, dass eine Betriebssystemversion ausgeführt wird, die IPv6 unterstützt. Stellen Sie zudem sicher, dass das Betriebssystem und die Netzwerkklassen ordnungsgemäß konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="ae832-104">To use the IPv6 protocol, ensure that you are running a version of the operating system that supports IPv6 and ensure that the operating system and the networking classes are configured properly.</span></span>  
  
## <a name="configuration-steps"></a><span data-ttu-id="ae832-105">Konfigurationsschritte</span><span class="sxs-lookup"><span data-stu-id="ae832-105">Configuration Steps</span></span>  
 <span data-ttu-id="ae832-106">In der folgenden Tabelle werden verschiedene Konfigurationen aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="ae832-106">The following table lists various configurations</span></span>  
  
|<span data-ttu-id="ae832-107">Ist Betriebssystem IPv6-fähig?</span><span class="sxs-lookup"><span data-stu-id="ae832-107">Operating system IPv6-enabled?</span></span>|<span data-ttu-id="ae832-108">Sind Netzwerkklassen IPv6-fähig?</span><span class="sxs-lookup"><span data-stu-id="ae832-108">Networking classes IPv6-enabled?</span></span>|<span data-ttu-id="ae832-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ae832-109">Description</span></span>|  
|-------------------------------------|---------------------------------------|-----------------|  
|<span data-ttu-id="ae832-110">Nein</span><span class="sxs-lookup"><span data-stu-id="ae832-110">No</span></span>|<span data-ttu-id="ae832-111">Nein</span><span class="sxs-lookup"><span data-stu-id="ae832-111">No</span></span>|<span data-ttu-id="ae832-112">Kann IPv6-Adressen analysieren.</span><span class="sxs-lookup"><span data-stu-id="ae832-112">Can parse IPv6 addresses.</span></span>|  
|<span data-ttu-id="ae832-113">Nein</span><span class="sxs-lookup"><span data-stu-id="ae832-113">No</span></span>|<span data-ttu-id="ae832-114">Ja</span><span class="sxs-lookup"><span data-stu-id="ae832-114">Yes</span></span>|<span data-ttu-id="ae832-115">Kann IPv6-Adressen analysieren.</span><span class="sxs-lookup"><span data-stu-id="ae832-115">Can parse IPv6 addresses.</span></span>|  
|<span data-ttu-id="ae832-116">Ja</span><span class="sxs-lookup"><span data-stu-id="ae832-116">Yes</span></span>|<span data-ttu-id="ae832-117">Nein</span><span class="sxs-lookup"><span data-stu-id="ae832-117">No</span></span>|<span data-ttu-id="ae832-118">Kann IPv6-Adressen analysieren und mithilfe von nicht als veraltet markierten Methoden zur Namensauflösung auflösen.</span><span class="sxs-lookup"><span data-stu-id="ae832-118">Can parse IPv6 addresses and resolve IPv6 addresses using name resolution methods not marked obsolete.</span></span>|  
|<span data-ttu-id="ae832-119">Ja</span><span class="sxs-lookup"><span data-stu-id="ae832-119">Yes</span></span>|<span data-ttu-id="ae832-120">Ja</span><span class="sxs-lookup"><span data-stu-id="ae832-120">Yes</span></span>|<span data-ttu-id="ae832-121">Kann IPv6-Adressen analysieren und mithilfe von allen Methoden auflösen, einschließlich der als veraltet markierten Methoden.</span><span class="sxs-lookup"><span data-stu-id="ae832-121">Can parse and resolve IPv6 addresses using all methods including those marked obsolete.</span></span>|  
  
 <span data-ttu-id="ae832-122">Bedenken Sie, dass Sie zum Aktivieren der IPv6-Unterstützung für alle Klassen im System.Net-Namespace die Computerkonfigurationsdatei oder die Konfigurationsdatei für die Anwendung ändern müssen.</span><span class="sxs-lookup"><span data-stu-id="ae832-122">Be aware that to enable the IPv6 support for all classes in the System.Net namespace, you must modify the computer configuration file or the configuration file for the application.</span></span> <span data-ttu-id="ae832-123">Die Konfigurationsdatei für die Anwendung hat Vorrang vor der Computerkonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="ae832-123">The configuration file for an application has precedence over the computer configuration file.</span></span>  
  
 <span data-ttu-id="ae832-124">Ein Beispiel, wie Sie die Computerkonfigurationsdatei *machine.config* ändern, um die Ipv6-Unterstützung zu aktivieren, finden Sie unter [Vorgehensweise: Ändern der Computerkonfigurationsdatei zum Aktivieren der Ipv6-Unterstützung](how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).</span><span class="sxs-lookup"><span data-stu-id="ae832-124">For an example of how to modify the computer configuration file, *machine.config*, to enable Ipv6 support see, [How to: Modify the Computer Configuration File to Enable Ipv6 Support](how-to-modify-the-computer-configuration-file-to-enable-ipv6-support.md).</span></span> <span data-ttu-id="ae832-125">Stellen Sie außerdem sicher, dass die IPv6-Unterstützung für das Betriebssystem aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ae832-125">Also, ensure that the IPv6 support is enabled for the operating system.</span></span>  
  
 <span data-ttu-id="ae832-126">.NET Framework verfügt über einen Konfigurationsschalter, der in einer Konfigurationsdatei wie folgt festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="ae832-126">The .NET Framework has a configuration switch set in a configuration file as follows</span></span>  
  
```xml  
<system.net>  
  ...  
  <settings>  
    ...  
    <ipv6 enabled="true"/>  
    ...  
  </settings>  
  ...  
</system.net>  
```  
  
 <span data-ttu-id="ae832-127">Für .NET Framework Version 1.1 und früher gibt der Wert des Konfigurationsschalters **ipv6 enabled** an, ob Member der Klasse <xref:System.Net.Dns?displayProperty=nameWithType> IPv6-Adressen zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="ae832-127">For .NET Framework version 1.1 and earlier, the value of the **ipv6 enabled** configuration switch specifies whether members of the <xref:System.Net.Dns?displayProperty=nameWithType> class return IPv6 addresses.</span></span>  
  
 <span data-ttu-id="ae832-128">Für .NET Framework Version 2.0 und höher geben Member der Klasse <xref:System.Net.Dns?displayProperty=nameWithType> (z.B. die <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType>-Methode), sofern Windows IPv6 unterstützt, IPv6-Adressen mit einer Einschränkung zurück.</span><span class="sxs-lookup"><span data-stu-id="ae832-128">For .NET Framework version 2.0 and later, if Windows supports IPv6, then members of the <xref:System.Net.Dns?displayProperty=nameWithType> class, (for example, the <xref:System.Net.Dns.GetHostEntry%2A?displayProperty=nameWithType> method), will return IPv6 addresses with one limitation.</span></span> <span data-ttu-id="ae832-129">Veraltete Member der DNS <xref:System.Net.Dns?displayProperty=nameWithType> (z.B. die <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType>-Methode) lesen und erkennen den Wert in der Konfigurationsdatei für die IPv6-aktivierte Einstellung.</span><span class="sxs-lookup"><span data-stu-id="ae832-129">Obsolete members of the DNS <xref:System.Net.Dns?displayProperty=nameWithType> (for example, the <xref:System.Net.Dns.Resolve%2A?displayProperty=nameWithType> method) will read and recognize the value in the configuration file for the ipv6 enabled setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae832-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae832-130">See also</span></span>

- [<span data-ttu-id="ae832-131">Internetprotokoll Version 6</span><span class="sxs-lookup"><span data-stu-id="ae832-131">Internet Protocol Version 6</span></span>](internet-protocol-version-6.md)
- [<span data-ttu-id="ae832-132">Sockets</span><span class="sxs-lookup"><span data-stu-id="ae832-132">Sockets</span></span>](sockets.md)
- [<span data-ttu-id="ae832-133">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ae832-133">Network Settings Schema</span></span>](../configure-apps/file-schema/network/index.md)
- [<span data-ttu-id="ae832-134">\<ipv6>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ae832-134">\<ipv6> Element (Network Settings)</span></span>](../configure-apps/file-schema/network/ipv6-element-network-settings.md)
