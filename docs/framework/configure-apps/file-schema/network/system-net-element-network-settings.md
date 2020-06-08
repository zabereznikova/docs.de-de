---
title: <system.Net>-Element (Netzwerkeinstellungen)
description: Das <System.net> Network settings-Element enthält Einstellungen, die angeben, wie die .NET Framework eine Verbindung mit den Netzwerkoptionen in der .NET Framework herstellt.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
ms.openlocfilehash: 9f18c7a3586948c03391d609f437e216a91bc27f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504484"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="5c89f-103">\<system.Net>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="5c89f-103">\<system.Net> Element (Network Settings)</span></span>
<span data-ttu-id="5c89f-104">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5c89f-104">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.net>**  
  
## <a name="syntax"></a><span data-ttu-id="5c89f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5c89f-105">Syntax</span></span>  
  
```xml  
<system.net>
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c89f-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5c89f-106">Attributes and Elements</span></span>  
 <span data-ttu-id="5c89f-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5c89f-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c89f-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="5c89f-108">Attributes</span></span>  
 <span data-ttu-id="5c89f-109">Keine</span><span class="sxs-lookup"><span data-stu-id="5c89f-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5c89f-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5c89f-110">Child Elements</span></span>  
  
|<span data-ttu-id="5c89f-111">**Element**</span><span class="sxs-lookup"><span data-stu-id="5c89f-111">**Element**</span></span>|<span data-ttu-id="5c89f-112">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="5c89f-112">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="5c89f-113">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="5c89f-113">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="5c89f-114">Gibt Module an, die zum Authentifizieren von Internet Anforderungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5c89f-114">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="5c89f-115">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="5c89f-115">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="5c89f-116">Gibt die maximale Anzahl von Verbindungen mit einem Internet Host an.</span><span class="sxs-lookup"><span data-stu-id="5c89f-116">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="5c89f-117">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="5c89f-117">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="5c89f-118">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="5c89f-118">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="5c89f-119">mailSettings</span><span class="sxs-lookup"><span data-stu-id="5c89f-119">mailSettings</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="5c89f-120">Konfiguriert SMTP (Simple Mail Transport Protocol)-e-Mail-Sende Optionen.</span><span class="sxs-lookup"><span data-stu-id="5c89f-120">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="5c89f-121">requestCaching</span><span class="sxs-lookup"><span data-stu-id="5c89f-121">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="5c89f-122">Steuert den zwischen Speicherungs Mechanismus für Netzwerk Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="5c89f-122">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="5c89f-123">settings</span><span class="sxs-lookup"><span data-stu-id="5c89f-123">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="5c89f-124">Konfiguriert grundlegende Netzwerkoptionen für Klassen in den <xref:System.Net> zugehörigen untergeordneten Namespaces.</span><span class="sxs-lookup"><span data-stu-id="5c89f-124">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="5c89f-125">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="5c89f-125">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="5c89f-126">Gibt Module an, die zum Anfordern von Informationen von Internet Hosts verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5c89f-126">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5c89f-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5c89f-127">Parent Elements</span></span>  
  
|<span data-ttu-id="5c89f-128">**Element**</span><span class="sxs-lookup"><span data-stu-id="5c89f-128">**Element**</span></span>|<span data-ttu-id="5c89f-129">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="5c89f-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="5c89f-130">configuration</span><span class="sxs-lookup"><span data-stu-id="5c89f-130">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="5c89f-131">Enthält Einstellungen für alle Namespaces.</span><span class="sxs-lookup"><span data-stu-id="5c89f-131">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c89f-132">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="5c89f-132">Remarks</span></span>  
 <span data-ttu-id="5c89f-133">Das [\<system.net>](system-net-element-network-settings.md) -Element enthält Einstellungen für Klassen in den zugehörigen untergeordneten <xref:System.Net> Namespaces.</span><span class="sxs-lookup"><span data-stu-id="5c89f-133">The [\<system.net>](system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="5c89f-134">Die Einstellungen konfigurieren Authentifizierungs Module, Verbindungs Verwaltung, e-Mail-Einstellungen, den Proxy Server und Internet Anforderungs Module zum Empfangen von Informationen von Internet Hosts.</span><span class="sxs-lookup"><span data-stu-id="5c89f-134">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c89f-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c89f-135">Example</span></span>  
 <span data-ttu-id="5c89f-136">Das folgende Beispiel zeigt eine typische Konfiguration, die von-Klassen verwendet wird <xref:System.Net> .</span><span class="sxs-lookup"><span data-stu-id="5c89f-136">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient" />  
      <add type="System.Net.NegotiateClient" />  
      <add type="System.Net.KerberosClient" />  
      <add type="System.Net.NtlmClient" />  
      <add type="System.Net.BasicClient" />  
    </authenticationModules>  
    <connectionManagement>  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="https"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="file"  
           type="System.Net.FileWebRequestCreator"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5c89f-137">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="5c89f-137">See also</span></span>

- [<span data-ttu-id="5c89f-138">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="5c89f-138">Network Settings Schema</span></span>](index.md)
