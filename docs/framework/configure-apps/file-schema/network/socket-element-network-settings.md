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
ms.openlocfilehash: 5e8ec13a0bb991accff080db502552e46913c66d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64607507"
---
# <a name="socket-element-network-settings"></a><span data-ttu-id="043f8-102">\<Socket >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="043f8-102">\<socket> Element (Network Settings)</span></span>
<span data-ttu-id="043f8-103">Gibt an, ob es sich bei Socketvorgänge Abschlussports verwenden.</span><span class="sxs-lookup"><span data-stu-id="043f8-103">Specifies whether socket operations use completion ports.</span></span>  
  
 <span data-ttu-id="043f8-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="043f8-104">\<configuration></span></span>  
<span data-ttu-id="043f8-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="043f8-105">\<system.net></span></span>  
<span data-ttu-id="043f8-106">\<settings></span><span class="sxs-lookup"><span data-stu-id="043f8-106">\<settings></span></span>  
<span data-ttu-id="043f8-107">\<socket></span><span class="sxs-lookup"><span data-stu-id="043f8-107">\<socket></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="043f8-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="043f8-108">Syntax</span></span>  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="043f8-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="043f8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="043f8-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="043f8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="043f8-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="043f8-111">Attributes</span></span>  
  
|<span data-ttu-id="043f8-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="043f8-112">**Attribute**</span></span>|<span data-ttu-id="043f8-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="043f8-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|<span data-ttu-id="043f8-114">Gibt an, ob der Socket immer Komplettierungsports für Accept-Methodenaufrufe verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="043f8-114">Indicates whether the socket should always use completion ports for Accept method calls.</span></span> <span data-ttu-id="043f8-115">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="043f8-115">The default value is `false`.</span></span>|  
|`alwaysUseCompletionPortsForConnect`|<span data-ttu-id="043f8-116">Gibt an, ob der Socket immer Komplettierungsports für Connect Methodenaufrufe verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="043f8-116">Indicates whether the socket should always use completion ports for Connect method calls.</span></span> <span data-ttu-id="043f8-117">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="043f8-117">The default value is `false`.</span></span>|  
|`ipProtectionLevel`|<span data-ttu-id="043f8-118">Gibt die Standardvordergrundfarbe für <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> für einen Socket verwenden.</span><span class="sxs-lookup"><span data-stu-id="043f8-118">Specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="043f8-119">Der Standardwert hängt von der Version von Windows.</span><span class="sxs-lookup"><span data-stu-id="043f8-119">The default value depends on the version of Windows.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="043f8-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="043f8-120">Child Elements</span></span>  
 <span data-ttu-id="043f8-121">Keine</span><span class="sxs-lookup"><span data-stu-id="043f8-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="043f8-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="043f8-122">Parent Elements</span></span>  
  
|<span data-ttu-id="043f8-123">**Element**</span><span class="sxs-lookup"><span data-stu-id="043f8-123">**Element**</span></span>|<span data-ttu-id="043f8-124">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="043f8-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="043f8-125">settings</span><span class="sxs-lookup"><span data-stu-id="043f8-125">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="043f8-126">Konfiguriert grundlegende Netzwerkoptionen für den <xref:System.Net>-Namespace.</span><span class="sxs-lookup"><span data-stu-id="043f8-126">Configures basic network options for the <xref:System.Net> namespace.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="043f8-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="043f8-127">Remarks</span></span>  
 <span data-ttu-id="043f8-128">Die `alwaysUseCompletionPortsForAccept` und `alwaysUseCompletionPortsForConnect` Attribute werden an das Standardverhalten in Bezug auf die Verwendung von Abschlussanschlüsse verwendet, von den Klassen in der <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace.</span><span class="sxs-lookup"><span data-stu-id="043f8-128">The `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes are used to specify the default behavior regarding the use of completion ports by the classes in the <xref:System.Net.Sockets?displayProperty=nameWithType>.namespace.</span></span> <span data-ttu-id="043f8-129">Abschlussports werden für Anwendungen mit hoher Leistungsfähigkeit Server empfohlen.</span><span class="sxs-lookup"><span data-stu-id="043f8-129">Completion ports are recommended for high performance server applications.</span></span>  
  
 <span data-ttu-id="043f8-130">Der Standardwert für die `alwaysUseCompletionPortsForAccept` und `alwaysUseCompletionPortsForConnect` Attribute **"false"**.</span><span class="sxs-lookup"><span data-stu-id="043f8-130">The default value for the `alwaysUseCompletionPortsForAccept` and `alwaysUseCompletionPortsForConnect` attributes is **false**.</span></span>  
  
 <span data-ttu-id="043f8-131">Die <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> können verwendet werden, um den aktuellen Wert der erste der `alwaysUseCompletionPortsForAccept` Attribut aus anwendbaren Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="043f8-131">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> can be used to get the current value of the `alwaysUseCompletionPortsForAccept` attribute from applicable configuration files.</span></span> <span data-ttu-id="043f8-132">Die <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> können verwendet werden, um den aktuellen Wert der erste der `alwaysUseCompletionPortsForConnect` Attribut aus anwendbaren Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="043f8-132">The <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> can be used to get the current value of the `alwaysUseCompletionPortsForConnect` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="043f8-133">Die `ipProtectionLevel` Attribut gibt die Standardvordergrundfarbe für <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> für einen Socket verwenden.</span><span class="sxs-lookup"><span data-stu-id="043f8-133">The `ipProtectionLevel` attribute specifies the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> to use for a socket.</span></span> <span data-ttu-id="043f8-134">Die <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> -Eigenschaft ermöglicht das Konfigurieren einer Einschränkung eines IPv6-Sockets auf einen angegebenen Bereich, z. B. Adressen mit demselben linklokalen oder standortlokalen Präfix.</span><span class="sxs-lookup"><span data-stu-id="043f8-134">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property enables configuration of a restriction for an IPv6 socket to a specified scope, such as addresses with the same link local or site local prefix.</span></span> <span data-ttu-id="043f8-135">Diese Option ermöglicht es Anwendungen zugriffseinschränkungen für IPv6-Sockets zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="043f8-135">This option enables applications to place access restrictions on IPv6 sockets.</span></span> <span data-ttu-id="043f8-136">Mit solchen Einschränkungen kann sich eine im privaten LAN ausgeführte Anwendung selbst einfach und stabil vor externen Angriffen schützen.</span><span class="sxs-lookup"><span data-stu-id="043f8-136">Such restrictions enable an application running on a private LAN to simply and robustly harden itself against external attacks.</span></span> <span data-ttu-id="043f8-137">Diese Option erweitert oder beschränkt den Bereich eines empfangsbereiten Sockets, ermöglicht uneingeschränkten Zugriff von öffentlichen und privaten Benutzern bei Bedarf oder Einschränken des Zugriffs nur auf die denselben Standort erforderlich.</span><span class="sxs-lookup"><span data-stu-id="043f8-137">This option widens or narrows the scope of a listening socket, enabling unrestricted access from public and private users when appropriate, or restricting access only to the same site, as required.</span></span>  
  
 <span data-ttu-id="043f8-138">Dies `ipProtectionLevel` attributeinstellung wirkt sich auf nur die ersten eingehenden Datenverkehr:</span><span class="sxs-lookup"><span data-stu-id="043f8-138">This `ipProtectionLevel` attribute setting affects only initial incoming traffic:</span></span>  
  
- <span data-ttu-id="043f8-139">Ein TCP-Server lauscht für eingehende Verbindungen für einen Socket.</span><span class="sxs-lookup"><span data-stu-id="043f8-139">A TCP server listening for incoming connections on a socket.</span></span>  
  
- <span data-ttu-id="043f8-140">Eine UDP-Anwendung empfangen eines Pakets auf einem Socket.</span><span class="sxs-lookup"><span data-stu-id="043f8-140">A UDP application receiving a packet on a socket.</span></span>  
  
 <span data-ttu-id="043f8-141">Diese Einstellung wirkt sich nicht auf bereits eingerichtete TCP-Verbindungen (Datenverkehr ist in beide Richtungen unrestricted) und wirkt sich nicht auf eine Anwendung, die UDP-Pakete zu senden.</span><span class="sxs-lookup"><span data-stu-id="043f8-141">This configuration setting does not affect already established TCP connections (traffic is unrestricted in both directions) and does not affect an application sending UDP packets.</span></span>  
  
 <span data-ttu-id="043f8-142">Die möglichen Werte für die `ipProtectionLevel` Einstellung des Attributs entsprechen den Werten der definierten Schutzebenen angegeben, der <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> Enumeration wie folgt:</span><span class="sxs-lookup"><span data-stu-id="043f8-142">The possible values for the `ipProtectionLevel` attribute setting correspond with the defined protection levels specified in the <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> enumeration as follows:</span></span>  
  
|<span data-ttu-id="043f8-143">**Attributwert**</span><span class="sxs-lookup"><span data-stu-id="043f8-143">**Attribute Value**</span></span>|<span data-ttu-id="043f8-144">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="043f8-144">**Description**</span></span>|  
|-|-|  
|<span data-ttu-id="043f8-145">EdgeRestricted</span><span class="sxs-lookup"><span data-stu-id="043f8-145">EdgeRestricted</span></span>|<span data-ttu-id="043f8-146">Die IP-Schutzebene ist Edge beschränkt.</span><span class="sxs-lookup"><span data-stu-id="043f8-146">The IP protection level is edge restricted.</span></span> <span data-ttu-id="043f8-147">Dieser Wert wird von Anwendungen entwickelt, um den Betrieb über das Internet verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="043f8-147">This value would be used by applications designed to operate across the Internet.</span></span> <span data-ttu-id="043f8-148">Diese Einstellung lässt keine (Network Address Translation, NAT) durchlaufen, die unter Verwendung der Windows Teredo-Implementierung.</span><span class="sxs-lookup"><span data-stu-id="043f8-148">This setting does not allow Network Address Translation (NAT) traversal using the Windows Teredo implementation.</span></span> <span data-ttu-id="043f8-149">Diese Anwendungen können IPv4-Firewalls umgehen, damit Anwendungen vor auf den geöffneten Anschluss geleitet Internetangriffen geschützt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="043f8-149">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="043f8-150">Unter Windows Server 2003 und Windows XP ist der Standardwert für die IP-Schutzebene für einen Socket-Edge beschränkt.</span><span class="sxs-lookup"><span data-stu-id="043f8-150">On Windows Server 2003 and Windows XP, the default value for the IP Protection level on a socket is edge restricted.</span></span>|  
|<span data-ttu-id="043f8-151">Eingeschränkter Zugriff</span><span class="sxs-lookup"><span data-stu-id="043f8-151">Restricted</span></span>|<span data-ttu-id="043f8-152">Die IP-Schutzebene ist eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="043f8-152">The IP protection level is restricted.</span></span> <span data-ttu-id="043f8-153">Dieser Wert wird von Intranetanwendungen verwendet werden, die keine Internetszenarios implementieren.</span><span class="sxs-lookup"><span data-stu-id="043f8-153">This value would be used by intranet applications that do not implement Internet scenarios.</span></span> <span data-ttu-id="043f8-154">Diese Anwendungen sind im Allgemeinen nicht getestet oder Angriffe Internetformat festgeschrieben.</span><span class="sxs-lookup"><span data-stu-id="043f8-154">These applications are generally not tested or hardened against Internet-style attacks.</span></span> <span data-ttu-id="043f8-155">Diese Einstellung wird den empfangenen Datenverkehr auf linklokalen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="043f8-155">This setting will limit the received traffic to link-local only.</span></span>|  
|<span data-ttu-id="043f8-156">Uneingeschränkt</span><span class="sxs-lookup"><span data-stu-id="043f8-156">Unrestricted</span></span>|<span data-ttu-id="043f8-157">Die IP-Schutzebene ist nicht eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="043f8-157">The IP protection level is unrestricted.</span></span> <span data-ttu-id="043f8-158">Dieser Wert wird von Anwendungen entwickelt, um den Betrieb über das Internet, einschließlich Anwendungen profitieren von IPv6-NAT-Traversal-Funktionen integriert in Windows (z. B. Teredo).</span><span class="sxs-lookup"><span data-stu-id="043f8-158">This value would be used by applications designed to operate across the Internet, including applications taking advantage of IPv6 NAT traversal capabilities built into Windows (Teredo, for example).</span></span> <span data-ttu-id="043f8-159">Diese Anwendungen können IPv4-Firewalls umgehen, damit Anwendungen vor auf den geöffneten Anschluss geleitet Internetangriffen geschützt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="043f8-159">These applications may bypass IPv4 firewalls, so applications must be hardened against Internet attacks directed at the opened port.</span></span> <span data-ttu-id="043f8-160">Unter Windows Server 2008 R2 und Windows Vista ist der Standardwert für die IP-Schutzebene für einen Socket nicht eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="043f8-160">On Windows Server 2008 R2 and Windows Vista, the default value for the IP Protection level on a socket is unrestricted.</span></span>|  
|<span data-ttu-id="043f8-161">Nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="043f8-161">Unspecified</span></span>|<span data-ttu-id="043f8-162">Die IP-Schutzebene ist nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="043f8-162">The IP protection level is unspecified.</span></span> <span data-ttu-id="043f8-163">Auf Windows 7 und Windows Server 2008 R2 ist der Standardwert für die IP-Schutzebene für einen Socket nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="043f8-163">On Windows 7 and Windows Server 2008 R2, the default value for the IP Protection level on a socket is unspecified.</span></span>|  
  
 <span data-ttu-id="043f8-164">Der Standardwert für die `ipProtectionLevel` Attribut **Unspecified**.</span><span class="sxs-lookup"><span data-stu-id="043f8-164">The default value for the `ipProtectionLevel` attribute is **Unspecified**.</span></span>  
  
 <span data-ttu-id="043f8-165">Die <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> Eigenschaft kann verwendet werden, um den aktuellen Wert der erhalten die `ipProtectionLevel` Attribut aus anwendbaren Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="043f8-165">The <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> property can be used to get the current value of the `ipProtectionLevel` attribute from applicable configuration files.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="043f8-166">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="043f8-166">Configuration Files</span></span>  
 <span data-ttu-id="043f8-167">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="043f8-167">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="043f8-168">Beispiel</span><span class="sxs-lookup"><span data-stu-id="043f8-168">Example</span></span>  
 <span data-ttu-id="043f8-169">Das folgende Beispiel zeigt, wie Sie angeben, dass Abschlussanschlüsse verwendet werden soll und dass der Standardwert <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> sollte nicht eingeschränkt werden.</span><span class="sxs-lookup"><span data-stu-id="043f8-169">The following example shows how to specify that completion ports should be used and that the default <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> should be unrestricted.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="043f8-170">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="043f8-170">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>
- [<span data-ttu-id="043f8-171">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="043f8-171">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
