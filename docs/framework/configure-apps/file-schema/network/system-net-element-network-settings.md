---
title: <system.Net>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
ms.openlocfilehash: 810e942394c75c192e4423afe4c674ef3a2b9900
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697510"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="f630c-102">\<system.Net>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="f630c-102">\<system.Net> Element (Network Settings)</span></span>
<span data-ttu-id="f630c-103">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f630c-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
[<span data-ttu-id="f630c-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="f630c-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="f630c-105">&nbsp;&nbsp; **\<System. net >**</span><span class="sxs-lookup"><span data-stu-id="f630c-105">&nbsp;&nbsp;**\<system.net>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f630c-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f630c-106">Syntax</span></span>  
  
```xml  
<system.net>   
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f630c-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f630c-107">Attributes and Elements</span></span>  
 <span data-ttu-id="f630c-108">In den folgenden Abschnitten werden die Attribute, untergeordneten und übergeordneten Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f630c-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f630c-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="f630c-109">Attributes</span></span>  
 <span data-ttu-id="f630c-110">None.</span><span class="sxs-lookup"><span data-stu-id="f630c-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f630c-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f630c-111">Child Elements</span></span>  
  
|<span data-ttu-id="f630c-112">**Element**</span><span class="sxs-lookup"><span data-stu-id="f630c-112">**Element**</span></span>|<span data-ttu-id="f630c-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="f630c-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f630c-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="f630c-114">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="f630c-115">Gibt Module an, die zum Authentifizieren von Internet Anforderungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f630c-115">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="f630c-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="f630c-116">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="f630c-117">Gibt die maximale Anzahl von Verbindungen mit einem Internet Host an.</span><span class="sxs-lookup"><span data-stu-id="f630c-117">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="f630c-118">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="f630c-118">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="f630c-119">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="f630c-119">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="f630c-120">mailSettings</span><span class="sxs-lookup"><span data-stu-id="f630c-120">mailSettings</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="f630c-121">Konfiguriert SMTP (Simple Mail Transport Protocol)-e-Mail-Sende Optionen.</span><span class="sxs-lookup"><span data-stu-id="f630c-121">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="f630c-122">requestCaching</span><span class="sxs-lookup"><span data-stu-id="f630c-122">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="f630c-123">Steuert den zwischen Speicherungs Mechanismus für Netzwerk Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="f630c-123">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="f630c-124">settings</span><span class="sxs-lookup"><span data-stu-id="f630c-124">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="f630c-125">Konfiguriert grundlegende Netzwerkoptionen für Klassen in den <xref:System.Net> und verwandten untergeordneten Namespaces.</span><span class="sxs-lookup"><span data-stu-id="f630c-125">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="f630c-126">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="f630c-126">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="f630c-127">Gibt Module an, die zum Anfordern von Informationen von Internet Hosts verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f630c-127">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f630c-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f630c-128">Parent Elements</span></span>  
  
|<span data-ttu-id="f630c-129">**Element**</span><span class="sxs-lookup"><span data-stu-id="f630c-129">**Element**</span></span>|<span data-ttu-id="f630c-130">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="f630c-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f630c-131">configuration</span><span class="sxs-lookup"><span data-stu-id="f630c-131">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="f630c-132">Enthält Einstellungen für alle Namespaces.</span><span class="sxs-lookup"><span data-stu-id="f630c-132">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f630c-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f630c-133">Remarks</span></span>  
 <span data-ttu-id="f630c-134">Das [\<System. net >](system-net-element-network-settings.md) -Element enthält Einstellungen für Klassen im <xref:System.Net> und verwandten untergeordneten Namespaces.</span><span class="sxs-lookup"><span data-stu-id="f630c-134">The [\<system.net>](system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="f630c-135">Die Einstellungen konfigurieren Authentifizierungs Module, Verbindungs Verwaltung, e-Mail-Einstellungen, den Proxy Server und Internet Anforderungs Module zum Empfangen von Informationen von Internet Hosts.</span><span class="sxs-lookup"><span data-stu-id="f630c-135">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f630c-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f630c-136">Example</span></span>  
 <span data-ttu-id="f630c-137">Das folgende Beispiel zeigt eine typische Konfiguration, die von <xref:System.Net>-Klassen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f630c-137">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f630c-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f630c-138">See also</span></span>

- [<span data-ttu-id="f630c-139">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="f630c-139">Network Settings Schema</span></span>](index.md)
