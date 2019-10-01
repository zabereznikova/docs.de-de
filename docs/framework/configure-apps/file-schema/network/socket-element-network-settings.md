---
title: <socket>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket
- http://schemas.microsoft.com/.NetConfiguration/v2.0#socket
helpviewer_keywords:
- <socket> element
- socket element
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
ms.openlocfilehash: ec2c8388411e24940041dc9dcb7f6a6755e89805
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697587"
---
# <a name="socket-element-network-settings"></a><span data-ttu-id="2e0dd-102">\<socket >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="2e0dd-102">\<socket> Element (Network Settings)</span></span>
<span data-ttu-id="2e0dd-103">Gibt an, ob Socketvorgänge Beendigungs Ports verwenden.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-103">Specifies whether socket operations use completion ports.</span></span>  
  
[<span data-ttu-id="2e0dd-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="2e0dd-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="2e0dd-105">&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="2e0dd-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="2e0dd-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<settings >** ](settings-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="2e0dd-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)</span></span>  
<span data-ttu-id="2e0dd-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<socket >**</span><span class="sxs-lookup"><span data-stu-id="2e0dd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<socket>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e0dd-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="2e0dd-108">Syntax</span></span>  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e0dd-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2e0dd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2e0dd-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e0dd-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="2e0dd-111">Attributes</span></span>  
  
|<span data-ttu-id="2e0dd-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="2e0dd-112">**Attribute**</span></span>|<span data-ttu-id="2e0dd-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2e0dd-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|<span data-ttu-id="2e0dd-114">Gibt an, ob der Socket immer Beendigungs Anschlüsse für Accept-Methodenaufrufe verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-114">Indicates whether the socket should always use completion ports for Accept method calls.</span></span> <span data-ttu-id="2e0dd-115">Der Standardwert ist `false`sein.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-115">The default value is `false`.</span></span>|  
|`alwaysUseCompletionPortsForConnect`|<span data-ttu-id="2e0dd-116">Gibt an, ob der Socket immer Beendigungs Anschlüsse für Verbindungsmethoden Aufrufe verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-116">Indicates whether the socket should always use completion ports for Connect method calls.</span></span> <span data-ttu-id="2e0dd-117">Der Standardwert ist `false`sein.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-117">The default value is `false`.</span></span>|  
|`ipProtectionLevel`|<span data-ttu-id="2e0dd-118">Gibt den Standard <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> an, der für einen Socket verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-118">Specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="2e0dd-119">Der Standardwert hängt von der Windows-Version ab.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-119">The default value depends on the version of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2e0dd-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2e0dd-120">Child Elements</span></span>  
 <span data-ttu-id="2e0dd-121">Keine</span><span class="sxs-lookup"><span data-stu-id="2e0dd-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2e0dd-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2e0dd-122">Parent Elements</span></span>  
  
|<span data-ttu-id="2e0dd-123">**Element**</span><span class="sxs-lookup"><span data-stu-id="2e0dd-123">**Element**</span></span>|<span data-ttu-id="2e0dd-124">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2e0dd-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2e0dd-125">settings</span><span class="sxs-lookup"><span data-stu-id="2e0dd-125">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="2e0dd-126">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-126">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e0dd-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2e0dd-127">Remarks</span></span>  
 <span data-ttu-id="2e0dd-128">Die Attribute `alwaysUseCompletionPortsForAccept` und `alwaysUseCompletionPortsForConnect` werden verwendet, um das Standardverhalten in Bezug auf die Verwendung von Abschlussports durch die Klassen im @no__t -2. Namespace anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-128">The `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes are used to specify the default behavior regarding the use of completion ports by the classes in the <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace.</span></span> <span data-ttu-id="2e0dd-129">Abschlussports werden für hochleistungsfähige Server Anwendungen empfohlen.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-129">Completion ports are recommended for high performance server applications.</span></span>  
  
 <span data-ttu-id="2e0dd-130">Der Standardwert für die Attribute `alwaysUseCompletionPortsForAccept` und `alwaysUseCompletionPortsForConnect` ist **false**.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-130">The default value for the `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes is **false**.</span></span>  
  
 <span data-ttu-id="2e0dd-131">Der <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> kann verwendet werden, um den aktuellen Wert des `alwaysUseCompletionPortsForAccept`-Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-131">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> can be used to get the current value of the `alwaysUseCompletionPortsForAccept` attribute from applicable configuration files.</span></span> <span data-ttu-id="2e0dd-132">Der <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> kann verwendet werden, um den aktuellen Wert des `alwaysUseCompletionPortsForConnect`-Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-132">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> can be used to get the current value of the `alwaysUseCompletionPortsForConnect` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="2e0dd-133">Das `ipProtectionLevel`-Attribut gibt die Standard <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> an, die für einen Socket verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-133">The `ipProtectionLevel` attribute specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="2e0dd-134">Die <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A>-Eigenschaft ermöglicht die Konfiguration einer Einschränkung für einen IPv6-Socket zu einem angegebenen Bereich, z. b. Adressen mit demselben Link lokalen oder Standort lokalen Präfix.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-134">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property enables configuration of a restriction for an IPv6 socket to a specified scope, such as addresses with the same link local or site local prefix.</span></span> <span data-ttu-id="2e0dd-135">Mit dieser Option können Anwendungen Zugriffs Einschränkungen für IPv6-Sockets platzieren.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-135">This option enables applications to place access restrictions on IPv6 sockets.</span></span> <span data-ttu-id="2e0dd-136">Mit solchen Einschränkungen kann sich eine im privaten LAN ausgeführte Anwendung selbst einfach und stabil vor externen Angriffen schützen.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-136">Such restrictions enable an application running on a private LAN to simply and robustly harden itself against external attacks.</span></span> <span data-ttu-id="2e0dd-137">Mit dieser Option wird der Bereich eines Abhör Sockets erweitert oder eingeschränkt, bei Bedarf der uneingeschränkte Zugriff von öffentlichen und privaten Benutzern ermöglicht oder der Zugriff auf dieselbe Website eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-137">This option widens or narrows the scope of a listening socket, enabling unrestricted access from public and private users when appropriate, or restricting access only to the same site, as required.</span></span>  
  
 <span data-ttu-id="2e0dd-138">Diese @no__t 0-Attribut Einstellung wirkt sich nur auf den ersten eingehenden Datenverkehr aus:</span><span class="sxs-lookup"><span data-stu-id="2e0dd-138">This `ipProtectionLevel` attribute setting affects only initial incoming traffic:</span></span>  
  
- <span data-ttu-id="2e0dd-139">Ein TCP-Server, der eingehende Verbindungen für einen Socket überwacht.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-139">A TCP server listening for incoming connections on a socket.</span></span>  
  
- <span data-ttu-id="2e0dd-140">Eine UDP-Anwendung, die ein Paket für einen Socket empfängt.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-140">A UDP application receiving a packet on a socket.</span></span>  
  
 <span data-ttu-id="2e0dd-141">Diese Konfigurationseinstellung wirkt sich nicht auf bereits festgelegte TCP-Verbindungen aus (Datenverkehr ist in beiden Richtungen uneingeschränkt) und wirkt sich nicht auf eine Anwendung aus, die UDP-Pakete sendet.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-141">This configuration setting does not affect already established TCP connections (traffic is unrestricted in both directions) and does not affect an application sending UDP packets.</span></span>  
  
 <span data-ttu-id="2e0dd-142">Die möglichen Werte für die `ipProtectionLevel`-Attribut Einstellung entsprechen den definierten, in der <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>-Enumeration angegebenen Schutz Ebenen wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2e0dd-142">The possible values for the `ipProtectionLevel` attribute setting correspond with the defined protection levels specified in the <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumeration as follows:</span></span>  
  
|<span data-ttu-id="2e0dd-143">**Attribut Wert**</span><span class="sxs-lookup"><span data-stu-id="2e0dd-143">**Attribute Value**</span></span>|<span data-ttu-id="2e0dd-144">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2e0dd-144">**Description**</span></span>|  
|-|-|  
|<span data-ttu-id="2e0dd-145">Edgerestrihiert</span><span class="sxs-lookup"><span data-stu-id="2e0dd-145">EdgeRestricted</span></span>|<span data-ttu-id="2e0dd-146">Die IP-Schutz Ebene ist Edge-eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-146">The IP protection level is edge restricted.</span></span> <span data-ttu-id="2e0dd-147">Dieser Wert wird von Anwendungen verwendet, die für den Betrieb über das Internet konzipiert sind.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-147">This value would be used by applications designed to operate across the Internet.</span></span> <span data-ttu-id="2e0dd-148">Diese Einstellung lässt die NAT-Überquerung (Network Address Translation) nicht zu, da die Teredo-Implementierung von Windows verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-148">This setting does not allow Network Address Translation (NAT) traversal using the Windows Teredo implementation.</span></span> <span data-ttu-id="2e0dd-149">Diese Anwendungen können IPv4-Firewalls umgehen, sodass Anwendungen gegen Internet Angriffe auf den geöffneten Port festgeschrieben werden müssen.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-149">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="2e0dd-150">Unter Windows Server 2003 und Windows XP ist Edge restricted der Standardwert für die IP-Schutz Ebene für einen Socket.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-150">On Windows Server 2003 and Windows XP, the default value for the IP Protection level on a socket is edge restricted.</span></span>|  
|<span data-ttu-id="2e0dd-151">Eingeschränkter Zugriff</span><span class="sxs-lookup"><span data-stu-id="2e0dd-151">Restricted</span></span>|<span data-ttu-id="2e0dd-152">Die IP-Schutz Ebene ist eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-152">The IP protection level is restricted.</span></span> <span data-ttu-id="2e0dd-153">Dieser Wert wird von Intranetanwendungen verwendet, die keine Internet Szenarios implementieren.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-153">This value would be used by intranet applications that do not implement Internet scenarios.</span></span> <span data-ttu-id="2e0dd-154">Diese Anwendungen werden in der Regel nicht getestet oder gegen Angriffe im Internet untersucht.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-154">These applications are generally not tested or hardened against Internet-style attacks.</span></span> <span data-ttu-id="2e0dd-155">Mit dieser Einstellung wird der empfangene Datenverkehr nur auf Link-Local beschränkt.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-155">This setting will limit the received traffic to link-local only.</span></span>|  
|<span data-ttu-id="2e0dd-156">Uneingeschränkt</span><span class="sxs-lookup"><span data-stu-id="2e0dd-156">Unrestricted</span></span>|<span data-ttu-id="2e0dd-157">Die IP-Schutz Ebene ist uneingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-157">The IP protection level is unrestricted.</span></span> <span data-ttu-id="2e0dd-158">Dieser Wert wird von Anwendungen verwendet, die für den gesamten Internet Betrieb entwickelt wurden, einschließlich Anwendungen, die die in Windows integrierten IPv6-NAT-Traversale-Funktionen nutzen (z. b. Teredo).</span><span class="sxs-lookup"><span data-stu-id="2e0dd-158">This value would be used by applications designed to operate across the Internet, including applications taking advantage of IPv6 NAT traversal capabilities built into Windows (Teredo, for example).</span></span> <span data-ttu-id="2e0dd-159">Diese Anwendungen können IPv4-Firewalls umgehen, sodass Anwendungen gegen Internet Angriffe auf den geöffneten Port festgeschrieben werden müssen.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-159">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="2e0dd-160">Unter Windows Server 2008 R2 und Windows Vista ist der Standardwert für die IP-Schutz Ebene für einen Socket uneingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-160">On Windows Server 2008 R2 and Windows Vista, the default value for the IP Protection level on a socket is unrestricted.</span></span>|  
|<span data-ttu-id="2e0dd-161">Nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-161">Unspecified</span></span>|<span data-ttu-id="2e0dd-162">Die IP-Schutz Ebene ist nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-162">The IP protection level is unspecified.</span></span> <span data-ttu-id="2e0dd-163">Unter Windows 7 und Windows Server 2008 R2 ist der Standardwert für die IP-Schutz Ebene für einen Socket nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-163">On Windows 7 and Windows Server 2008 R2, the default value for the IP Protection level on a socket is unspecified.</span></span>|  
  
 <span data-ttu-id="2e0dd-164">Der Standardwert für das `ipProtectionLevel`-Attribut ist **nicht angegeben**.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-164">The default value for the `ipProtectionLevel` attribute is **Unspecified**.</span></span>  
  
 <span data-ttu-id="2e0dd-165">Die <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A>-Eigenschaft kann verwendet werden, um den aktuellen Wert des `ipProtectionLevel`-Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-165">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property can be used to get the current value of the `ipProtectionLevel` attribute from applicable configuration files.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="2e0dd-166">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="2e0dd-166">Configuration Files</span></span>  
 <span data-ttu-id="2e0dd-167">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-167">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e0dd-168">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2e0dd-168">Example</span></span>  
 <span data-ttu-id="2e0dd-169">Im folgenden Beispiel wird gezeigt, wie angegeben wird, dass die Abschlussports verwendet werden sollen und dass der Standardwert von <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> uneingeschränkt sein sollte.</span><span class="sxs-lookup"><span data-stu-id="2e0dd-169">The following example shows how to specify that completion ports should be used and that the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> should be unrestricted.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <socket  
        alwaysUseCompletionPortsForAccept="true"  
        alwaysUseCompletionPortsForConnect="true"  
        ipProtectionLevel="Unrestricted"  
       />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2e0dd-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e0dd-170">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>
- [<span data-ttu-id="2e0dd-171">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="2e0dd-171">Network Settings Schema</span></span>](index.md)
