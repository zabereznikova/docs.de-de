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
ms.openlocfilehash: b8df32745007b2a145d35b8cfcc4cbd2bd17eb33
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201732"
---
# <a name="socket-element-network-settings"></a><span data-ttu-id="fc03e-102">\<socket>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="fc03e-102">\<socket> Element (Network Settings)</span></span>

<span data-ttu-id="fc03e-103">Gibt an, ob Socketvorgänge Beendigungs Ports verwenden.</span><span class="sxs-lookup"><span data-stu-id="fc03e-103">Specifies whether socket operations use completion ports.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<settings>**](settings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<socket>**

## <a name="syntax"></a><span data-ttu-id="fc03e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fc03e-104">Syntax</span></span>  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc03e-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fc03e-105">Attributes and Elements</span></span>  

 <span data-ttu-id="fc03e-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fc03e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc03e-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="fc03e-107">Attributes</span></span>  
  
|<span data-ttu-id="fc03e-108">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="fc03e-108">**Attribute**</span></span>|<span data-ttu-id="fc03e-109">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="fc03e-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|<span data-ttu-id="fc03e-110">Gibt an, ob der Socket immer Beendigungs Anschlüsse für Accept-Methodenaufrufe verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="fc03e-110">Indicates whether the socket should always use completion ports for Accept method calls.</span></span> <span data-ttu-id="fc03e-111">Standardwert: `false`.</span><span class="sxs-lookup"><span data-stu-id="fc03e-111">The default value is `false`.</span></span>|  
|`alwaysUseCompletionPortsForConnect`|<span data-ttu-id="fc03e-112">Gibt an, ob der Socket immer Beendigungs Anschlüsse für Verbindungsmethoden Aufrufe verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="fc03e-112">Indicates whether the socket should always use completion ports for Connect method calls.</span></span> <span data-ttu-id="fc03e-113">Standardwert: `false`.</span><span class="sxs-lookup"><span data-stu-id="fc03e-113">The default value is `false`.</span></span>|  
|`ipProtectionLevel`|<span data-ttu-id="fc03e-114">Gibt den Standardwert <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> an, der für einen Socket verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fc03e-114">Specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="fc03e-115">Der Standardwert hängt von der Windows-Version ab.</span><span class="sxs-lookup"><span data-stu-id="fc03e-115">The default value depends on the version of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc03e-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fc03e-116">Child Elements</span></span>  

 <span data-ttu-id="fc03e-117">Keine</span><span class="sxs-lookup"><span data-stu-id="fc03e-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fc03e-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fc03e-118">Parent Elements</span></span>  
  
|<span data-ttu-id="fc03e-119">**Element**</span><span class="sxs-lookup"><span data-stu-id="fc03e-119">**Element**</span></span>|<span data-ttu-id="fc03e-120">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="fc03e-120">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="fc03e-121">settings</span><span class="sxs-lookup"><span data-stu-id="fc03e-121">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="fc03e-122">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="fc03e-122">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc03e-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fc03e-123">Remarks</span></span>  

 <span data-ttu-id="fc03e-124">Das `alwaysUseCompletionPortsForAccept` -Attribut und das- `alwaysUseCompletionPortsForConnect` Attribut werden verwendet, um das Standardverhalten in Bezug auf die Verwendung von Abschlussports durch die Klassen im <xref:System.Net.Sockets?displayProperty=nameWithType> .-Namespace anzugeben.</span><span class="sxs-lookup"><span data-stu-id="fc03e-124">The `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes are used to specify the default behavior regarding the use of completion ports by the classes in the <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace.</span></span> <span data-ttu-id="fc03e-125">Abschlussports werden für hochleistungsfähige Server Anwendungen empfohlen.</span><span class="sxs-lookup"><span data-stu-id="fc03e-125">Completion ports are recommended for high performance server applications.</span></span>  
  
 <span data-ttu-id="fc03e-126">Der Standardwert für das `alwaysUseCompletionPortsForAccept` -Attribut und das- `alwaysUseCompletionPortsForConnect` Attribut ist **false**.</span><span class="sxs-lookup"><span data-stu-id="fc03e-126">The default value for the `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes is **false**.</span></span>  
  
 <span data-ttu-id="fc03e-127"><xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A>Kann verwendet werden, um den aktuellen Wert des `alwaysUseCompletionPortsForAccept` Attributs aus anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="fc03e-127">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> can be used to get the current value of the `alwaysUseCompletionPortsForAccept` attribute from applicable configuration files.</span></span> <span data-ttu-id="fc03e-128"><xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A>Kann verwendet werden, um den aktuellen Wert des `alwaysUseCompletionPortsForConnect` Attributs aus anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="fc03e-128">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> can be used to get the current value of the `alwaysUseCompletionPortsForConnect` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="fc03e-129">Das- `ipProtectionLevel` Attribut gibt den <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> für einen Socket zu verwendenden Standardwert an.</span><span class="sxs-lookup"><span data-stu-id="fc03e-129">The `ipProtectionLevel` attribute specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="fc03e-130">Die- <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> Eigenschaft ermöglicht die Konfiguration einer Einschränkung für einen IPv6-Socket zu einem angegebenen Bereich, z. b. Adressen mit demselben Link lokalen oder Standort lokalen Präfix.</span><span class="sxs-lookup"><span data-stu-id="fc03e-130">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property enables configuration of a restriction for an IPv6 socket to a specified scope, such as addresses with the same link local or site local prefix.</span></span> <span data-ttu-id="fc03e-131">Mit dieser Option können Anwendungen Zugriffs Einschränkungen für IPv6-Sockets platzieren.</span><span class="sxs-lookup"><span data-stu-id="fc03e-131">This option enables applications to place access restrictions on IPv6 sockets.</span></span> <span data-ttu-id="fc03e-132">Mit solchen Einschränkungen kann sich eine im privaten LAN ausgeführte Anwendung selbst einfach und stabil vor externen Angriffen schützen.</span><span class="sxs-lookup"><span data-stu-id="fc03e-132">Such restrictions enable an application running on a private LAN to simply and robustly harden itself against external attacks.</span></span> <span data-ttu-id="fc03e-133">Mit dieser Option wird der Bereich eines Abhör Sockets erweitert oder eingeschränkt, bei Bedarf der uneingeschränkte Zugriff von öffentlichen und privaten Benutzern ermöglicht oder der Zugriff auf dieselbe Website eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="fc03e-133">This option widens or narrows the scope of a listening socket, enabling unrestricted access from public and private users when appropriate, or restricting access only to the same site, as required.</span></span>  
  
 <span data-ttu-id="fc03e-134">Diese `ipProtectionLevel` Attribut Einstellung betrifft nur den ersten eingehenden Datenverkehr:</span><span class="sxs-lookup"><span data-stu-id="fc03e-134">This `ipProtectionLevel` attribute setting affects only initial incoming traffic:</span></span>  
  
- <span data-ttu-id="fc03e-135">Ein TCP-Server, der eingehende Verbindungen für einen Socket überwacht.</span><span class="sxs-lookup"><span data-stu-id="fc03e-135">A TCP server listening for incoming connections on a socket.</span></span>  
  
- <span data-ttu-id="fc03e-136">Eine UDP-Anwendung, die ein Paket für einen Socket empfängt.</span><span class="sxs-lookup"><span data-stu-id="fc03e-136">A UDP application receiving a packet on a socket.</span></span>  
  
 <span data-ttu-id="fc03e-137">Diese Konfigurationseinstellung wirkt sich nicht auf bereits festgelegte TCP-Verbindungen aus (Datenverkehr ist in beiden Richtungen uneingeschränkt) und wirkt sich nicht auf eine Anwendung aus, die UDP-Pakete sendet.</span><span class="sxs-lookup"><span data-stu-id="fc03e-137">This configuration setting does not affect already established TCP connections (traffic is unrestricted in both directions) and does not affect an application sending UDP packets.</span></span>  
  
 <span data-ttu-id="fc03e-138">Die möglichen Werte für die- `ipProtectionLevel` Attribut Einstellung entsprechen den definierten, in der-Enumeration angegebenen Schutz Ebenen <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> wie folgt:</span><span class="sxs-lookup"><span data-stu-id="fc03e-138">The possible values for the `ipProtectionLevel` attribute setting correspond with the defined protection levels specified in the <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumeration as follows:</span></span>  
  
|<span data-ttu-id="fc03e-139">**Attributwert**</span><span class="sxs-lookup"><span data-stu-id="fc03e-139">**Attribute Value**</span></span>|<span data-ttu-id="fc03e-140">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="fc03e-140">**Description**</span></span>|  
|-|-|  
|<span data-ttu-id="fc03e-141">Edgerestrihiert</span><span class="sxs-lookup"><span data-stu-id="fc03e-141">EdgeRestricted</span></span>|<span data-ttu-id="fc03e-142">Die IP-Schutzebene ist auf den Netzwerk-Edge beschränkt.</span><span class="sxs-lookup"><span data-stu-id="fc03e-142">The IP protection level is edge restricted.</span></span> <span data-ttu-id="fc03e-143">Dieser Wert wird von Anwendungen verwendet, die für den Betrieb über das Internet konzipiert sind.</span><span class="sxs-lookup"><span data-stu-id="fc03e-143">This value would be used by applications designed to operate across the Internet.</span></span> <span data-ttu-id="fc03e-144">Diese Einstellung lässt die NAT-Überquerung (Netzwerkadressenübersetzung) mithilfe der Windows Teredo-Implementierung nicht zu.</span><span class="sxs-lookup"><span data-stu-id="fc03e-144">This setting does not allow Network Address Translation (NAT) traversal using the Windows Teredo implementation.</span></span> <span data-ttu-id="fc03e-145">Diese Anwendungen können IPv4-Firewalls umgehen und müssen daher vor Internetangriffen auf den geöffneten Anschluss geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="fc03e-145">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="fc03e-146">Unter Windows Server 2003 und Windows XP ist der Standardwert für die IP-Schutzebene für einen Socket "EdgeRestricted".</span><span class="sxs-lookup"><span data-stu-id="fc03e-146">On Windows Server 2003 and Windows XP, the default value for the IP Protection level on a socket is edge restricted.</span></span>|  
|<span data-ttu-id="fc03e-147">Eingeschränkt</span><span class="sxs-lookup"><span data-stu-id="fc03e-147">Restricted</span></span>|<span data-ttu-id="fc03e-148">Die IP-Schutzebene ist eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="fc03e-148">The IP protection level is restricted.</span></span> <span data-ttu-id="fc03e-149">Dieser Wert wird von Intranetanwendungen verwendet, die keine Internetszenarios implementieren.</span><span class="sxs-lookup"><span data-stu-id="fc03e-149">This value would be used by intranet applications that do not implement Internet scenarios.</span></span> <span data-ttu-id="fc03e-150">Diese Anwendungen werden im Allgemeinen nicht getestet oder vor Internetangriffen geschützt.</span><span class="sxs-lookup"><span data-stu-id="fc03e-150">These applications are generally not tested or hardened against Internet-style attacks.</span></span> <span data-ttu-id="fc03e-151">Diese Einstellung beschränkt den empfangenen Datenverkehr auf linklokalen Datenverkehr.</span><span class="sxs-lookup"><span data-stu-id="fc03e-151">This setting will limit the received traffic to link-local only.</span></span>|  
|<span data-ttu-id="fc03e-152">Nicht eingeschränkt</span><span class="sxs-lookup"><span data-stu-id="fc03e-152">Unrestricted</span></span>|<span data-ttu-id="fc03e-153">Die IP-Schutzebene ist nicht eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="fc03e-153">The IP protection level is unrestricted.</span></span> <span data-ttu-id="fc03e-154">Dieser Wert wird von Anwendungen verwendet, die für den Betrieb über das Internet konzipiert sind. Dazu zählen Anwendungen, die in Windows integrierte IPv6-NAT-Überquerungsfunktionen nutzen (z. B. Teredo).</span><span class="sxs-lookup"><span data-stu-id="fc03e-154">This value would be used by applications designed to operate across the Internet, including applications taking advantage of IPv6 NAT traversal capabilities built into Windows (Teredo, for example).</span></span> <span data-ttu-id="fc03e-155">Diese Anwendungen können IPv4-Firewalls umgehen und müssen daher vor Internetangriffen auf den geöffneten Anschluss geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="fc03e-155">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="fc03e-156">Unter Windows Server 2008 R2 und Windows Vista ist der Standardwert für die IP-Schutzebene für einen Socket "Unrestricted".</span><span class="sxs-lookup"><span data-stu-id="fc03e-156">On Windows Server 2008 R2 and Windows Vista, the default value for the IP Protection level on a socket is unrestricted.</span></span>|  
|<span data-ttu-id="fc03e-157">Nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="fc03e-157">Unspecified</span></span>|<span data-ttu-id="fc03e-158">Die IP-Schutzebene ist nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="fc03e-158">The IP protection level is unspecified.</span></span> <span data-ttu-id="fc03e-159">Unter Windows 7 und Windows Server 2008 R2 ist der Standardwert für die IP-Schutzebene für einen Socket "Unspecified".</span><span class="sxs-lookup"><span data-stu-id="fc03e-159">On Windows 7 and Windows Server 2008 R2, the default value for the IP Protection level on a socket is unspecified.</span></span>|  
  
 <span data-ttu-id="fc03e-160">Der Standardwert für das- `ipProtectionLevel` Attribut ist **nicht angegeben**.</span><span class="sxs-lookup"><span data-stu-id="fc03e-160">The default value for the `ipProtectionLevel` attribute is **Unspecified**.</span></span>  
  
 <span data-ttu-id="fc03e-161">Die- <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> Eigenschaft kann verwendet werden, um den aktuellen Wert des `ipProtectionLevel` Attributs aus den anwendbaren Konfigurationsdateien zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="fc03e-161">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property can be used to get the current value of the `ipProtectionLevel` attribute from applicable configuration files.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="fc03e-162">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="fc03e-162">Configuration Files</span></span>  

 <span data-ttu-id="fc03e-163">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fc03e-163">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc03e-164">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc03e-164">Example</span></span>  

 <span data-ttu-id="fc03e-165">Im folgenden Beispiel wird gezeigt, wie angegeben wird, dass die Abschlussports verwendet werden sollen und der Standardwert <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> uneingeschränkt sein sollte.</span><span class="sxs-lookup"><span data-stu-id="fc03e-165">The following example shows how to specify that completion ports should be used and that the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> should be unrestricted.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fc03e-166">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fc03e-166">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>
- [<span data-ttu-id="fc03e-167">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="fc03e-167">Network Settings Schema</span></span>](index.md)
