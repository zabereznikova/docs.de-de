---
title: Proxykonfiguration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "14"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 41f7cfe76acfb4b6bbf66207685935c190a51901
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="proxy-configuration"></a><span data-ttu-id="a2096-102">Proxykonfiguration</span><span class="sxs-lookup"><span data-stu-id="a2096-102">Proxy Configuration</span></span>
<span data-ttu-id="a2096-103">Ein Proxyserver verarbeitet Clientanforderungen für Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="a2096-103">A proxy server handles client requests for resources.</span></span> <span data-ttu-id="a2096-104">Ein Proxy kann eine angeforderte Ressource aus dem Cache zurückgeben oder die Anforderung an den Server weiterleiten, auf dem sich die Ressource befindet.</span><span class="sxs-lookup"><span data-stu-id="a2096-104">A proxy can return a requested resource from its cache or forward the request to the server where the resource resides.</span></span> <span data-ttu-id="a2096-105">Proxys können die Netzwerkleistung durch Reduzierung der Anzahl der an Remote-Server gesendeten Anforderungen verbessern.</span><span class="sxs-lookup"><span data-stu-id="a2096-105">Proxies can improve network performance by reducing the number of requests sent to remote servers.</span></span> <span data-ttu-id="a2096-106">Proxys können auch verwendet werden, um den Zugriff auf Ressourcen einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="a2096-106">Proxies can also be used to restrict access to resources.</span></span>  
  
## <a name="adaptive-proxies"></a><span data-ttu-id="a2096-107">Adaptive Proxys</span><span class="sxs-lookup"><span data-stu-id="a2096-107">Adaptive Proxies</span></span>  
 <span data-ttu-id="a2096-108">Im .NET Framework gibt es zwei Grundtypen von Proxys: adaptive und statische.</span><span class="sxs-lookup"><span data-stu-id="a2096-108">In the .NET Framework, proxies come in two varieties: adaptive and static.</span></span> <span data-ttu-id="a2096-109">Adaptive Proxys ändern Sie ihre Einstellungen, wenn sich die Konfiguration ändert.</span><span class="sxs-lookup"><span data-stu-id="a2096-109">Adaptive proxies adjust their settings when the network configuration changes.</span></span> <span data-ttu-id="a2096-110">Wenn z. B. ein Laptop-Benutzer eine DFÜ-Netzwerkverbindung gestartet hat, würde ein adaptiver Proxy diese Änderung erkennen, das neue Konfigurationsskript entdecken und ausführen und die Einstellungen entsprechend anpassen.</span><span class="sxs-lookup"><span data-stu-id="a2096-110">For example, if a laptop user starts a dialup network connection, an adaptive proxy would recognize this change, discover and run its new configuration script, and adjust its settings appropriately.</span></span>  
  
 <span data-ttu-id="a2096-111">Adaptive Proxys werden durch ein Konfigurationsskript konfiguriert (siehe [Automatische Proxyerkennung](../../../docs/framework/network-programming/automatic-proxy-detection.md)).</span><span class="sxs-lookup"><span data-stu-id="a2096-111">Adaptive proxies are configured by a configuration script (see [Automatic Proxy Detection](../../../docs/framework/network-programming/automatic-proxy-detection.md)).</span></span> <span data-ttu-id="a2096-112">Das Skript generiert eine Reihe von Anwendungsprotokollen und ein Proxy für jedes Protokoll.</span><span class="sxs-lookup"><span data-stu-id="a2096-112">The script generates a set of application protocols and a proxy for each protocol.</span></span>  
  
 <span data-ttu-id="a2096-113">Mehrere Optionen steuern, wie das Skript ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a2096-113">Several options control how the configuration script is run.</span></span> <span data-ttu-id="a2096-114">Sie können Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="a2096-114">You can specify the following:</span></span>  
  
-   <span data-ttu-id="a2096-115">Wie oft wird ist das Konfigurationsskript heruntergeladen und ausgeführt?</span><span class="sxs-lookup"><span data-stu-id="a2096-115">How often the configuration script is downloaded and run.</span></span>  
  
-   <span data-ttu-id="a2096-116">Wie lange gilt es zu warten, bis das Skript heruntergeladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="a2096-116">How long to wait for the script to download.</span></span>  
  
-   <span data-ttu-id="a2096-117">Welche Anmeldeinformationen Ihr System verwenden sollte, um auf den den Proxy zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="a2096-117">Which credentials your system should use to access the proxy.</span></span>  
  
-   <span data-ttu-id="a2096-118">Welche Anmeldeinformationen Ihr System zum Downloaden des Konfigurationsskripts verwenden sollte.</span><span class="sxs-lookup"><span data-stu-id="a2096-118">Which credentials your system should use to download the configuration script.</span></span>  
  
 <span data-ttu-id="a2096-119">Änderungen in der Netzwerkumgebung erfordern, dass das System einen neuen Satz von Proxys verwendet.</span><span class="sxs-lookup"><span data-stu-id="a2096-119">Changes in the network environment may require that the system use a new set of proxies.</span></span> <span data-ttu-id="a2096-120">Wenn eine Netzwerkverbindung ausfällt oder eine neue Netzwerkverbindung initialisiert wird, muss das System die entsprechende Quelle des Konfigurationsskripts in der neuen Umgebung erkennen und das neue Skript ausführen.</span><span class="sxs-lookup"><span data-stu-id="a2096-120">If a network connection goes down or a new network connection is initialized, the system must discover the appropriate source of the configuration script in the new environment and run the new script.</span></span>  
  
 <span data-ttu-id="a2096-121">Die folgende Tabelle zeigt die Konfigurationsoptionen für einen adaptiven Proxy.</span><span class="sxs-lookup"><span data-stu-id="a2096-121">The following table shows configuration options for an adaptive proxy.</span></span>  
  
|<span data-ttu-id="a2096-122">Attribut-, Eigenschafts- oder Konfigurationseinstellung</span><span class="sxs-lookup"><span data-stu-id="a2096-122">Attribute, property, or configuration file setting</span></span>|<span data-ttu-id="a2096-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2096-123">Description</span></span>|  
|--------------------------------------------------------|-----------------|  
|`scriptDownloadInterval`|<span data-ttu-id="a2096-124">Verstrichene Zeit in Sekunden zwischen den Script-Downloads.</span><span class="sxs-lookup"><span data-stu-id="a2096-124">Elapsed time in seconds between script downloads.</span></span>|  
|`scriptDownloadTimeout`|<span data-ttu-id="a2096-125">Wartezeit (in Sekunden) für das Skript-Download.</span><span class="sxs-lookup"><span data-stu-id="a2096-125">Time to wait (in seconds) for the script to download.</span></span>|  
|<span data-ttu-id="a2096-126">`useDefaultCredentials` oder <xref:System.Net.WebProxy.UseDefaultCredentials></span><span class="sxs-lookup"><span data-stu-id="a2096-126">`useDefaultCredentials` or <xref:System.Net.WebProxy.UseDefaultCredentials></span></span>|<span data-ttu-id="a2096-127">Steuert, ob das System die Standardanmeldeinformationen verwendet, um auf einen Proxy zugreifen.</span><span class="sxs-lookup"><span data-stu-id="a2096-127">Controls whether the system uses the default network credentials to access a proxy.</span></span>|  
|`useDefaultCredentialForScriptDownload`|<span data-ttu-id="a2096-128">Steuert, ob das System die Standardanmeldeinformationen verwendet, um das Skript herunterladen.</span><span class="sxs-lookup"><span data-stu-id="a2096-128">Controls whether the system uses the default network credentials to download the configuration script.</span></span>|  
|`usesystemdefaults`|<span data-ttu-id="a2096-129">Steuert, ob die statischen Proxyeinstellungen (Proxy-Adresse, Bypass-Liste und Bypass auf lokal) aus den Proxy-Einstellungen für den Benutzer im Internet Explorer gelesen werden sollte.</span><span class="sxs-lookup"><span data-stu-id="a2096-129">Controls whether the static proxy settings (proxy address, bypass list, and bypass on local) should be read from the Internet Explorer proxy settings for the user.</span></span> <span data-ttu-id="a2096-130">Wenn dieser Wert auf "True" gesetzt wird, dann werden die statischen Proxy-Einstellungen von Internet Explorer verwendet.</span><span class="sxs-lookup"><span data-stu-id="a2096-130">If this value is set to "true", then the static proxy settings from Internet Explorer will be used.</span></span><br /><br /> <span data-ttu-id="a2096-131">Wenn dieser Wert "false" lautet oder nicht gesetzt wird, dann können die statischen Proxy-Einstellungen in der Konfiguration angegeben werden und die Internet Explorer-Proxy-Einstellungen werden überschrieben.</span><span class="sxs-lookup"><span data-stu-id="a2096-131">If this value is "false" or not set, then the static proxy settings can be specified in the configuration and will override the Internet Explorer proxy settings.</span></span> <span data-ttu-id="a2096-132">Dieser Wert muss auch auf "false" gesetzt oder darf nicht festgelegt werden, damit adaptive Proxys aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="a2096-132">This value must also be set to "false" or not set for adaptive proxies to be enabled.</span></span>|  
  
 <span data-ttu-id="a2096-133">Das folgende Beispiel zeigt eine typische adaptive Proxykonfiguration.</span><span class="sxs-lookup"><span data-stu-id="a2096-133">The following example shows a typical adaptive proxy configuration.</span></span>  
  
```xml  
<system.net>  
    <defaultProxy>  
      <proxy  scriptDownloadInterval="600"  
              scriptDownloadTimeout="30"  
              useDefaultCredentials="true"  
              usesystemdefaults="true"  
      />  
    </defaultProxy>  
</system.net>  
```  
  
## <a name="static-proxies"></a><span data-ttu-id="a2096-134">Statische Proxys</span><span class="sxs-lookup"><span data-stu-id="a2096-134">Static Proxies</span></span>  
 <span data-ttu-id="a2096-135">Statische Proxys werden in der Regel explizit von einer Anwendung konfiguriert, oder wenn eine Konfigurationsdatei von einer Anwendung oder vom System aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a2096-135">Static proxies are usually configured explicitly by an application, or when a configuration file is invoked by an application or the system.</span></span> <span data-ttu-id="a2096-136">Statische Proxys sind in Netzwerken nützlich, in denen die Topologie sich nur selten verändert, wie z. B. bei einem Desktop-Computer, der mit einem Unternehmensnetzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="a2096-136">Static proxies are useful in networks in which the topology changes infrequently, such as a desktop computer connected to a corporate network.</span></span>  
  
 <span data-ttu-id="a2096-137">Mehrere Optionen steuern, wie ein statischer Proxy arbeitet.</span><span class="sxs-lookup"><span data-stu-id="a2096-137">Several options control how a static proxy operates.</span></span> <span data-ttu-id="a2096-138">Sie können Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="a2096-138">You can specify the following:</span></span>  
  
-   <span data-ttu-id="a2096-139">Die Proxy-Adresse.</span><span class="sxs-lookup"><span data-stu-id="a2096-139">The address of the proxy.</span></span>  
  
-   <span data-ttu-id="a2096-140">Gibt an, ob der Proxy für lokale Adressen umgangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="a2096-140">Whether the proxy should be bypassed for local addresses.</span></span>  
  
-   <span data-ttu-id="a2096-141">Gibt an, ob der Proxy für eine Gruppe von Adressen umgangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="a2096-141">Whether the proxy should be bypassed for a set of addresses.</span></span>  
  
 <span data-ttu-id="a2096-142">Die folgende Tabelle zeigt die Konfigurationsoptionen für einen statischen Proxy.</span><span class="sxs-lookup"><span data-stu-id="a2096-142">The following table shows the configuration options for a static proxy.</span></span>  
  
|<span data-ttu-id="a2096-143">Attribut-, Eigenschafts- oder Konfigurationseinstellung</span><span class="sxs-lookup"><span data-stu-id="a2096-143">Attribute, property, or configuration file setting</span></span>|<span data-ttu-id="a2096-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2096-144">Description</span></span>|  
|--------------------------------------------------------|-----------------|  
|<span data-ttu-id="a2096-145">`proxyaddress` oder <xref:System.Net.WebProxy.Address></span><span class="sxs-lookup"><span data-stu-id="a2096-145">`proxyaddress` or <xref:System.Net.WebProxy.Address></span></span>|<span data-ttu-id="a2096-146">Die Adresse des Proxyservers, der verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a2096-146">The address of the proxy to use.</span></span>|  
|<span data-ttu-id="a2096-147">`bypassonlocal` oder <xref:System.Net.WebProxy.BypassProxyOnLocal></span><span class="sxs-lookup"><span data-stu-id="a2096-147">`bypassonlocal` or <xref:System.Net.WebProxy.BypassProxyOnLocal></span></span>|<span data-ttu-id="a2096-148">Steuert, ob der Proxy für lokale Adressen umgangen wird.</span><span class="sxs-lookup"><span data-stu-id="a2096-148">Controls whether the proxy is bypassed for local addresses.</span></span>|  
|<span data-ttu-id="a2096-149">`bypasslist` oder <xref:System.Net.WebProxy.BypassArrayList></span><span class="sxs-lookup"><span data-stu-id="a2096-149">`bypasslist` or <xref:System.Net.WebProxy.BypassArrayList></span></span>|<span data-ttu-id="a2096-150">Beschreibt mit regulären Ausdrücken eine Reihe von Adressen, die den Proxyserver umgehen.</span><span class="sxs-lookup"><span data-stu-id="a2096-150">Describes, with regular expressions, a set of addresses that bypass the proxy.</span></span>|  
|`usesystemdefaults`|<span data-ttu-id="a2096-151">Steuert, ob die statischen Proxyeinstellungen (Proxy-Adresse, Bypass-Liste und Bypass auf lokal) aus den Proxy-Einstellungen für den Benutzer im Internet Explorer gelesen werden sollte.</span><span class="sxs-lookup"><span data-stu-id="a2096-151">Controls whether the static proxy settings (proxy address, bypass list, and bypass on local) should be read from the Internet Explorer proxy settings for the user.</span></span> <span data-ttu-id="a2096-152">Wenn dieser Wert auf "True" gesetzt wird, dann werden die statischen Proxy-Einstellungen von Internet Explorer verwendet.</span><span class="sxs-lookup"><span data-stu-id="a2096-152">If this value is set to "true", then the static proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="a2096-153">Wen auf dem .NET Framework 2.0 dieser Wert auf "True" festgelegt wird, werden die Internet Explorer-Proxy-Einstellungen nicht von anderen Proxy-Einstellungen in der Konfigurationsdatei überschrieben.</span><span class="sxs-lookup"><span data-stu-id="a2096-153">On .NET Framework 2.0 when this value is set to "true", the Internet Explorer proxy settings are not overridden by other proxy settings in the configuration file.</span></span> <span data-ttu-id="a2096-154">Auf dem .NET Framework 1.1 können die Internet Explorer-Proxy-Einstellungen von anderen Proxy-Einstellungen in der Konfigurationsdatei überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="a2096-154">On .NET Framework 1.1, the Internet Explorer proxy settings can be overridden by other proxy settings in the configuration file.</span></span><br /><br /> <span data-ttu-id="a2096-155">Wenn dieser Wert "false" lautet oder nicht gesetzt wird, dann können die statischen Proxy-Einstellungen in der Konfiguration angegeben werden und die Internet Explorer-Proxy-Einstellungen werden überschrieben.</span><span class="sxs-lookup"><span data-stu-id="a2096-155">If this value is "false" or not set, then the static proxy settings can be specified in the configuration and will override the Internet Explorer proxy settings.</span></span> <span data-ttu-id="a2096-156">Dieser Wert muss auch auf "false" gesetzt oder darf nicht festgelegt werden, damit adaptive Proxys aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="a2096-156">This value must also be set to "false" or not set for adaptive proxies to be enabled.</span></span>|  
  
 <span data-ttu-id="a2096-157">Das folgende Beispiel zeigt eine typische adaptive Proxykonfiguration.</span><span class="sxs-lookup"><span data-stu-id="a2096-157">The following example shows a typical static proxy configuration.</span></span>  
  
```xml  
<system.net>  
    <defaultProxy>  
        <proxy  proxyaddress="http://proxy.contoso.com:3128"  
                bypassonlocal="true"  
        />  
        <bypasslist>  
            <add address="[a-z]+.blueyonderairlines.com$" />  
        </bypasslist>  
    </defaultProxy>  
</system.net>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a2096-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2096-158">See Also</span></span>  
 <xref:System.Net.WebProxy>  
 <xref:System.Net.GlobalProxySelection>  
 [<span data-ttu-id="a2096-159">Automatische Proxyerkennung</span><span class="sxs-lookup"><span data-stu-id="a2096-159">Automatic Proxy Detection</span></span>](../../../docs/framework/network-programming/automatic-proxy-detection.md)
