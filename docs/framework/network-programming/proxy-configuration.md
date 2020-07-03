---
title: Proxykonfiguration
description: Hier erfahren Sie, wie Sie adaptive und statische Proxyserver konfigurieren. Durch die Proxyserverkonfiguration wird gesteuert, wie ein Proxyserver Clientanforderungen für Ressourcen verarbeitet.
ms.date: 06/18/2018
helpviewer_keywords:
- Networking
- adaptive proxies
- static proxies
- Network Resources
- Internet, proxy configuration
- proxies
- network, proxy configuration
- proxies, configuring
ms.assetid: 353c0a8b-4cee-44f6-8e65-60e286743df9
ms.openlocfilehash: 4d62f5736e9aa469be49d101e85851bc01b7c159
ms.sourcegitcommit: 6219b1e1feccb16d88656444210fed3297f5611e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2020
ms.locfileid: "85141604"
---
# <a name="proxy-configuration"></a><span data-ttu-id="be705-104">Proxykonfiguration</span><span class="sxs-lookup"><span data-stu-id="be705-104">Proxy Configuration</span></span>
<span data-ttu-id="be705-105">Ein Proxyserver verarbeitet Clientanforderungen für Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="be705-105">A proxy server handles client requests for resources.</span></span> <span data-ttu-id="be705-106">Ein Proxy kann eine angeforderte Ressource aus dem Cache zurückgeben oder die Anforderung an den Server weiterleiten, auf dem sich die Ressource befindet.</span><span class="sxs-lookup"><span data-stu-id="be705-106">A proxy can return a requested resource from its cache or forward the request to the server where the resource resides.</span></span> <span data-ttu-id="be705-107">Proxys können die Netzwerkleistung durch Reduzierung der Anzahl der an Remote-Server gesendeten Anforderungen verbessern.</span><span class="sxs-lookup"><span data-stu-id="be705-107">Proxies can improve network performance by reducing the number of requests sent to remote servers.</span></span> <span data-ttu-id="be705-108">Proxys können auch verwendet werden, um den Zugriff auf Ressourcen einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="be705-108">Proxies can also be used to restrict access to resources.</span></span>  
  
## <a name="adaptive-proxies"></a><span data-ttu-id="be705-109">Adaptive Proxys</span><span class="sxs-lookup"><span data-stu-id="be705-109">Adaptive Proxies</span></span>  
 <span data-ttu-id="be705-110">Im .NET Framework gibt es zwei Grundtypen von Proxys: adaptive und statische.</span><span class="sxs-lookup"><span data-stu-id="be705-110">In the .NET Framework, proxies come in two varieties: adaptive and static.</span></span> <span data-ttu-id="be705-111">Adaptive Proxys ändern Sie ihre Einstellungen, wenn sich die Konfiguration ändert.</span><span class="sxs-lookup"><span data-stu-id="be705-111">Adaptive proxies adjust their settings when the network configuration changes.</span></span> <span data-ttu-id="be705-112">Wenn z. B. ein Laptop-Benutzer eine DFÜ-Netzwerkverbindung gestartet hat, würde ein adaptiver Proxy diese Änderung erkennen, das neue Konfigurationsskript entdecken und ausführen und die Einstellungen entsprechend anpassen.</span><span class="sxs-lookup"><span data-stu-id="be705-112">For example, if a laptop user starts a dialup network connection, an adaptive proxy would recognize this change, discover and run its new configuration script, and adjust its settings appropriately.</span></span>  
  
 <span data-ttu-id="be705-113">Adaptive Proxys werden durch ein Konfigurationsskript konfiguriert (siehe [Automatische Proxyerkennung](automatic-proxy-detection.md)).</span><span class="sxs-lookup"><span data-stu-id="be705-113">Adaptive proxies are configured by a configuration script (see [Automatic Proxy Detection](automatic-proxy-detection.md)).</span></span> <span data-ttu-id="be705-114">Das Skript generiert eine Reihe von Anwendungsprotokollen und ein Proxy für jedes Protokoll.</span><span class="sxs-lookup"><span data-stu-id="be705-114">The script generates a set of application protocols and a proxy for each protocol.</span></span>  
  
 <span data-ttu-id="be705-115">Änderungen in der Netzwerkumgebung erfordern, dass das System einen neuen Satz von Proxys verwendet.</span><span class="sxs-lookup"><span data-stu-id="be705-115">Changes in the network environment may require that the system use a new set of proxies.</span></span> <span data-ttu-id="be705-116">Wenn eine Netzwerkverbindung ausfällt oder eine neue Netzwerkverbindung initialisiert wird, muss das System die entsprechende Quelle des Konfigurationsskripts in der neuen Umgebung erkennen und das neue Skript ausführen.</span><span class="sxs-lookup"><span data-stu-id="be705-116">If a network connection goes down or a new network connection is initialized, the system must discover the appropriate source of the configuration script in the new environment and run the new script.</span></span>  
  
 <span data-ttu-id="be705-117">Sie können das Attribut `usesystemdefault` des Elements [`<proxy>`](../configure-apps/file-schema/network/proxy-element-network-settings.md) in der Konfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="be705-117">You can use the `usesystemdefault` attribute of the [`<proxy>`](../configure-apps/file-schema/network/proxy-element-network-settings.md) element in your configuration file.</span></span> <span data-ttu-id="be705-118">Das `usesystemdefault`-Attribut steuert, ob die statischen Proxyeinstellungen (Proxy-Adresse, Proxyumgehungsliste und lokale Proxyumgehung) aus den Proxy-Einstellungen für den Benutzer im Internet Explorer gelesen werden sollten.</span><span class="sxs-lookup"><span data-stu-id="be705-118">The `usesystemdefault` attribute controls whether the static proxy settings (proxy address, bypass list, and bypass on local) should be read from the Internet Explorer proxy settings for the user.</span></span> <span data-ttu-id="be705-119">Wenn dieser Wert auf `true` festgelegt wird, werden die statischen Proxyeinstellungen von Internet Explorer verwendet.</span><span class="sxs-lookup"><span data-stu-id="be705-119">If this value is set to `true`, the static proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="be705-120">Wenn der Wert auf `false` oder gar nicht festgelegt ist, können die statischen Proxyeinstellungen in der Konfiguration angegeben werden. Sie überschreiben dann die Proxyeinstellungen von Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="be705-120">If this value is `false` or not set, the static proxy settings can be specified in the configuration and will override the Internet Explorer proxy settings.</span></span> <span data-ttu-id="be705-121">Dieser Wert muss auch auf `false` oder gar nicht festgelegt werden, damit adaptive Proxys aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="be705-121">This value must also be set to `false` or not set for adaptive proxies to be enabled.</span></span>  
  
 <span data-ttu-id="be705-122">Das folgende Beispiel zeigt eine typische adaptive Proxykonfiguration.</span><span class="sxs-lookup"><span data-stu-id="be705-122">The following example shows a typical adaptive proxy configuration.</span></span>  
  
```xml  
<system.net>  
    <defaultProxy>  
      <proxy usesystemdefault="false" />
    </defaultProxy>  
</system.net>  
```  
  
## <a name="static-proxies"></a><span data-ttu-id="be705-123">Statische Proxys</span><span class="sxs-lookup"><span data-stu-id="be705-123">Static Proxies</span></span>  
 <span data-ttu-id="be705-124">Statische Proxys werden in der Regel explizit von einer Anwendung konfiguriert, oder wenn eine Konfigurationsdatei von einer Anwendung oder vom System aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="be705-124">Static proxies are usually configured explicitly by an application, or when a configuration file is invoked by an application or the system.</span></span> <span data-ttu-id="be705-125">Statische Proxys sind in Netzwerken nützlich, in denen die Topologie sich nur selten verändert, wie z. B. bei einem Desktop-Computer, der mit einem Unternehmensnetzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="be705-125">Static proxies are useful in networks in which the topology changes infrequently, such as a desktop computer connected to a corporate network.</span></span>  
  
 <span data-ttu-id="be705-126">Mehrere Optionen steuern, wie ein statischer Proxy arbeitet.</span><span class="sxs-lookup"><span data-stu-id="be705-126">Several options control how a static proxy operates.</span></span> <span data-ttu-id="be705-127">Sie können Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="be705-127">You can specify the following:</span></span>  
  
- <span data-ttu-id="be705-128">Die Proxy-Adresse.</span><span class="sxs-lookup"><span data-stu-id="be705-128">The address of the proxy.</span></span>  
  
- <span data-ttu-id="be705-129">Gibt an, ob der Proxy für lokale Adressen umgangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="be705-129">Whether the proxy should be bypassed for local addresses.</span></span>  
  
- <span data-ttu-id="be705-130">Gibt an, ob der Proxy für eine Gruppe von Adressen umgangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="be705-130">Whether the proxy should be bypassed for a set of addresses.</span></span>  
  
 <span data-ttu-id="be705-131">Die folgende Tabelle zeigt die Konfigurationsoptionen für einen statischen Proxy.</span><span class="sxs-lookup"><span data-stu-id="be705-131">The following table shows the configuration options for a static proxy.</span></span>  
  
|<span data-ttu-id="be705-132">Attribut-, Eigenschafts- oder Konfigurationseinstellung</span><span class="sxs-lookup"><span data-stu-id="be705-132">Attribute, property, or configuration file setting</span></span>|<span data-ttu-id="be705-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="be705-133">Description</span></span>|  
|--------------------------------------------------------|-----------------|  
|<span data-ttu-id="be705-134">`proxyaddress` oder <xref:System.Net.WebProxy.Address></span><span class="sxs-lookup"><span data-stu-id="be705-134">`proxyaddress` or <xref:System.Net.WebProxy.Address></span></span>|<span data-ttu-id="be705-135">Die Adresse des Proxyservers, der verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="be705-135">The address of the proxy to use.</span></span>|  
|<span data-ttu-id="be705-136">`bypassonlocal` oder <xref:System.Net.WebProxy.BypassProxyOnLocal></span><span class="sxs-lookup"><span data-stu-id="be705-136">`bypassonlocal` or <xref:System.Net.WebProxy.BypassProxyOnLocal></span></span>|<span data-ttu-id="be705-137">Steuert, ob der Proxy für lokale Adressen umgangen wird.</span><span class="sxs-lookup"><span data-stu-id="be705-137">Controls whether the proxy is bypassed for local addresses.</span></span>|  
|<span data-ttu-id="be705-138">`bypasslist` oder <xref:System.Net.WebProxy.BypassArrayList></span><span class="sxs-lookup"><span data-stu-id="be705-138">`bypasslist` or <xref:System.Net.WebProxy.BypassArrayList></span></span>|<span data-ttu-id="be705-139">Beschreibt mit regulären Ausdrücken eine Reihe von Adressen, die den Proxyserver umgehen.</span><span class="sxs-lookup"><span data-stu-id="be705-139">Describes, with regular expressions, a set of addresses that bypass the proxy.</span></span>|  
|`usesystemdefault`|<span data-ttu-id="be705-140">Steuert, ob die statischen Proxyeinstellungen (Proxy-Adresse, Bypass-Liste und Bypass auf lokal) aus den Proxy-Einstellungen für den Benutzer im Internet Explorer gelesen werden sollte.</span><span class="sxs-lookup"><span data-stu-id="be705-140">Controls whether the static proxy settings (proxy address, bypass list, and bypass on local) should be read from the Internet Explorer proxy settings for the user.</span></span> <span data-ttu-id="be705-141">Wenn dieser Wert auf `true` festgelegt wird, werden die statischen Proxyeinstellungen von Internet Explorer verwendet.</span><span class="sxs-lookup"><span data-stu-id="be705-141">If this value is set to `true`, then the static proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="be705-142">Wenn dieser Wert in .NET Framework 2.0 auf `true` festgelegt wird, werden die Proxyeinstellungen von Internet Explorer nicht von anderen Proxyeinstellungen in der Konfigurationsdatei überschrieben.</span><span class="sxs-lookup"><span data-stu-id="be705-142">On .NET Framework 2.0 when this value is set to `true`, the Internet Explorer proxy settings are not overridden by other proxy settings in the configuration file.</span></span> <span data-ttu-id="be705-143">Auf dem .NET Framework 1.1 können die Internet Explorer-Proxy-Einstellungen von anderen Proxy-Einstellungen in der Konfigurationsdatei überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="be705-143">On .NET Framework 1.1, the Internet Explorer proxy settings can be overridden by other proxy settings in the configuration file.</span></span><br /><br /> <span data-ttu-id="be705-144">Wenn dieser Wert auf `false` oder gar nicht festgelegt wird, können die statischen Proxyeinstellungen in der Konfiguration angegeben werden. Sie überschreiben dann die Proxyeinstellungen von Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="be705-144">If this value is `false` or not set, then the static proxy settings can be specified in the configuration and will override the Internet Explorer proxy settings.</span></span> <span data-ttu-id="be705-145">Dieser Wert muss auch auf `false` oder gar nicht festgelegt werden, damit adaptive Proxys aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="be705-145">This value must also be set to `false` or not set for adaptive proxies to be enabled.</span></span>|  
  
 <span data-ttu-id="be705-146">Das folgende Beispiel zeigt eine typische adaptive Proxykonfiguration.</span><span class="sxs-lookup"><span data-stu-id="be705-146">The following example shows a typical static proxy configuration.</span></span>  
  
```xml  
<system.net>  
    <defaultProxy>  
        <proxy  proxyaddress="http://proxy.contoso.com:3128"  
                bypassonlocal="True"  
        />  
        <bypasslist>  
            <add address="[a-z]+.blueyonderairlines.com$" />  
        </bypasslist>  
    </defaultProxy>  
</system.net>  
```  
  
## <a name="see-also"></a><span data-ttu-id="be705-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be705-147">See also</span></span>

- <xref:System.Net.WebProxy>
- <xref:System.Net.GlobalProxySelection>
- [<span data-ttu-id="be705-148">Automatische Proxyerkennung</span><span class="sxs-lookup"><span data-stu-id="be705-148">Automatic Proxy Detection</span></span>](automatic-proxy-detection.md)
