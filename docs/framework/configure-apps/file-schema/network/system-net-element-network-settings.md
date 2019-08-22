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
ms.openlocfilehash: 449146612938700f59f5e2ec761526d1dc66a3fc
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663958"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="9ef21-102">\<system.Net>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="9ef21-102">\<system.Net> Element (Network Settings)</span></span>
<span data-ttu-id="9ef21-103">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="9ef21-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
 <span data-ttu-id="9ef21-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="9ef21-104">\<configuration></span></span>  
<span data-ttu-id="9ef21-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="9ef21-105">\<system.net></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ef21-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ef21-106">Syntax</span></span>  
  
```xml  
<system.net>   
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ef21-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9ef21-107">Attributes and Elements</span></span>  
 <span data-ttu-id="9ef21-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9ef21-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ef21-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="9ef21-109">Attributes</span></span>  
 <span data-ttu-id="9ef21-110">Keine</span><span class="sxs-lookup"><span data-stu-id="9ef21-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9ef21-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9ef21-111">Child Elements</span></span>  
  
|<span data-ttu-id="9ef21-112">**Element**</span><span class="sxs-lookup"><span data-stu-id="9ef21-112">**Element**</span></span>|<span data-ttu-id="9ef21-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="9ef21-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9ef21-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="9ef21-114">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="9ef21-115">Gibt Module an, die zum Authentifizieren von Internet Anforderungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9ef21-115">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="9ef21-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="9ef21-116">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="9ef21-117">Gibt die maximale Anzahl von Verbindungen mit einem Internet Host an.</span><span class="sxs-lookup"><span data-stu-id="9ef21-117">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="9ef21-118">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="9ef21-118">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="9ef21-119">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="9ef21-119">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="9ef21-120">mailSettings</span><span class="sxs-lookup"><span data-stu-id="9ef21-120">mailSettings</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="9ef21-121">Konfiguriert SMTP (Simple Mail Transport Protocol)-e-Mail-Sende Optionen.</span><span class="sxs-lookup"><span data-stu-id="9ef21-121">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="9ef21-122">requestCaching</span><span class="sxs-lookup"><span data-stu-id="9ef21-122">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="9ef21-123">Steuert den zwischen Speicherungs Mechanismus für Netzwerk Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="9ef21-123">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="9ef21-124">settings</span><span class="sxs-lookup"><span data-stu-id="9ef21-124">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="9ef21-125">Konfiguriert grundlegende Netzwerkoptionen für Klassen in den <xref:System.Net> zugehörigen untergeordneten Namespaces.</span><span class="sxs-lookup"><span data-stu-id="9ef21-125">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="9ef21-126">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="9ef21-126">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="9ef21-127">Gibt Module an, die zum Anfordern von Informationen von Internet Hosts verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9ef21-127">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9ef21-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9ef21-128">Parent Elements</span></span>  
  
|<span data-ttu-id="9ef21-129">**Element**</span><span class="sxs-lookup"><span data-stu-id="9ef21-129">**Element**</span></span>|<span data-ttu-id="9ef21-130">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="9ef21-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="9ef21-131">configuration</span><span class="sxs-lookup"><span data-stu-id="9ef21-131">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="9ef21-132">Enthält Einstellungen für alle Namespaces.</span><span class="sxs-lookup"><span data-stu-id="9ef21-132">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ef21-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9ef21-133">Remarks</span></span>  
 <span data-ttu-id="9ef21-134"><xref:System.Net> [ Das\<System. net >](system-net-element-network-settings.md) -Element enthält Einstellungen für Klassen in den zugehörigen untergeordneten Namespaces.</span><span class="sxs-lookup"><span data-stu-id="9ef21-134">The [\<system.net>](system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="9ef21-135">Die Einstellungen konfigurieren Authentifizierungs Module, Verbindungs Verwaltung, e-Mail-Einstellungen, den Proxy Server und Internet Anforderungs Module zum Empfangen von Informationen von Internet Hosts.</span><span class="sxs-lookup"><span data-stu-id="9ef21-135">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ef21-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9ef21-136">Example</span></span>  
 <span data-ttu-id="9ef21-137">Das folgende Beispiel zeigt eine typische Konfiguration, die <xref:System.Net> von-Klassen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9ef21-137">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9ef21-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ef21-138">See also</span></span>

- [<span data-ttu-id="9ef21-139">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="9ef21-139">Network Settings Schema</span></span>](index.md)
