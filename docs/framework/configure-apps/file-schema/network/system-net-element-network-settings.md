---
title: '&lt;system.Net&gt; -Element (Netzwerkeinstellungen)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
ms.openlocfilehash: 2f387ecccac2c1c97d03e2c22a31ad2dd0577c77
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54567775"
---
# <a name="ltsystemnetgt-element-network-settings"></a><span data-ttu-id="48e51-102">&lt;system.Net&gt; -Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="48e51-102">&lt;system.Net&gt; Element (Network Settings)</span></span>
<span data-ttu-id="48e51-103">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="48e51-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
 <span data-ttu-id="48e51-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="48e51-104">\<configuration></span></span>  
<span data-ttu-id="48e51-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="48e51-105">\<system.net></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48e51-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="48e51-106">Syntax</span></span>  
  
```xml  
<system.net>   
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48e51-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="48e51-107">Attributes and Elements</span></span>  
 <span data-ttu-id="48e51-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="48e51-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48e51-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="48e51-109">Attributes</span></span>  
 <span data-ttu-id="48e51-110">Keine</span><span class="sxs-lookup"><span data-stu-id="48e51-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="48e51-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="48e51-111">Child Elements</span></span>  
  
|<span data-ttu-id="48e51-112">**Element**</span><span class="sxs-lookup"><span data-stu-id="48e51-112">**Element**</span></span>|<span data-ttu-id="48e51-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="48e51-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="48e51-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="48e51-114">authenticationModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|<span data-ttu-id="48e51-115">Gibt die Module, die zum Authentifizieren von internetanforderungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="48e51-115">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="48e51-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="48e51-116">connectionManagement</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|<span data-ttu-id="48e51-117">Gibt die maximale Anzahl von Verbindungen mit einem Internethost an.</span><span class="sxs-lookup"><span data-stu-id="48e51-117">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="48e51-118">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="48e51-118">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="48e51-119">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="48e51-119">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="48e51-120">mailSettings</span><span class="sxs-lookup"><span data-stu-id="48e51-120">mailSettings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|<span data-ttu-id="48e51-121">Konfiguriert (SMTP, Simple Mail Transport Protocol) e-Mail-Sendeoptionen.</span><span class="sxs-lookup"><span data-stu-id="48e51-121">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="48e51-122">requestCaching</span><span class="sxs-lookup"><span data-stu-id="48e51-122">requestCaching</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|<span data-ttu-id="48e51-123">Steuert den Zwischenspeichermechanismus für netzwerkanforderungen.</span><span class="sxs-lookup"><span data-stu-id="48e51-123">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="48e51-124">settings</span><span class="sxs-lookup"><span data-stu-id="48e51-124">settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|<span data-ttu-id="48e51-125">Konfiguriert grundlegende Netzwerkoptionen für Klassen in der <xref:System.Net> und zugehörigen untergeordneten Namespaces.</span><span class="sxs-lookup"><span data-stu-id="48e51-125">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="48e51-126">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="48e51-126">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="48e51-127">Gibt die Module zum Anfordern von Informationen von Internethosts verwendet.</span><span class="sxs-lookup"><span data-stu-id="48e51-127">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="48e51-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="48e51-128">Parent Elements</span></span>  
  
|<span data-ttu-id="48e51-129">**Element**</span><span class="sxs-lookup"><span data-stu-id="48e51-129">**Element**</span></span>|<span data-ttu-id="48e51-130">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="48e51-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="48e51-131">configuration</span><span class="sxs-lookup"><span data-stu-id="48e51-131">configuration</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="48e51-132">Enthält Einstellungen für alle Namespaces.</span><span class="sxs-lookup"><span data-stu-id="48e51-132">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48e51-133">Hinweise</span><span class="sxs-lookup"><span data-stu-id="48e51-133">Remarks</span></span>  
 <span data-ttu-id="48e51-134">Die [ \<system.net >](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) Element enthält Einstellungen für Klassen in der <xref:System.Net> und zugehörigen untergeordneten Namespaces.</span><span class="sxs-lookup"><span data-stu-id="48e51-134">The [\<system.net>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="48e51-135">Die Einstellungen konfigurieren Authentifizierungsmodule, verbindungsverwaltung, e-Mail-Einstellungen, die webanwendungsproxy-Server und Internet-Anforderung Module zum Empfangen von Informationen von Internethosts.</span><span class="sxs-lookup"><span data-stu-id="48e51-135">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48e51-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="48e51-136">Example</span></span>  
 <span data-ttu-id="48e51-137">Das folgende Beispiel zeigt eine typische Konfiguration, die von verwendet <xref:System.Net> Klassen.</span><span class="sxs-lookup"><span data-stu-id="48e51-137">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="48e51-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48e51-138">See also</span></span>
- [<span data-ttu-id="48e51-139">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="48e51-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
