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
ms.openlocfilehash: 88098f2afaad9728e38c4f9935b45f45826a0ca9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154555"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="8f757-102">\<system.Net>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="8f757-102">\<system.Net> Element (Network Settings)</span></span>
<span data-ttu-id="8f757-103">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8f757-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
[<span data-ttu-id="8f757-104">**\<Konfiguration>**</span><span class="sxs-lookup"><span data-stu-id="8f757-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="8f757-105">&nbsp;&nbsp;**\<system.net>**</span><span class="sxs-lookup"><span data-stu-id="8f757-105">&nbsp;&nbsp;**\<system.net>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f757-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f757-106">Syntax</span></span>  
  
```xml  
<system.net>
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8f757-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8f757-107">Attributes and Elements</span></span>  
 <span data-ttu-id="8f757-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8f757-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8f757-109">Attributes</span><span class="sxs-lookup"><span data-stu-id="8f757-109">Attributes</span></span>  
 <span data-ttu-id="8f757-110">Keine.</span><span class="sxs-lookup"><span data-stu-id="8f757-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8f757-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8f757-111">Child Elements</span></span>  
  
|<span data-ttu-id="8f757-112">**Element**</span><span class="sxs-lookup"><span data-stu-id="8f757-112">**Element**</span></span>|<span data-ttu-id="8f757-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="8f757-113">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8f757-114">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="8f757-114">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="8f757-115">Gibt Module an, die zum Authentifizieren von Internetanforderungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8f757-115">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="8f757-116">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="8f757-116">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="8f757-117">Gibt die maximale Anzahl von Verbindungen zu einem Internethost an.</span><span class="sxs-lookup"><span data-stu-id="8f757-117">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="8f757-118">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="8f757-118">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="8f757-119">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="8f757-119">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="8f757-120">Mailsettings</span><span class="sxs-lookup"><span data-stu-id="8f757-120">mailSettings</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="8f757-121">Konfiguriert SMTP-E-Mail-Versandoptionen (Simple Mail Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="8f757-121">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="8f757-122">Requestcaching</span><span class="sxs-lookup"><span data-stu-id="8f757-122">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="8f757-123">Steuert den Zwischenspeicherungsmechanismus für Netzwerkanforderungen.</span><span class="sxs-lookup"><span data-stu-id="8f757-123">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="8f757-124">einstellungen</span><span class="sxs-lookup"><span data-stu-id="8f757-124">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="8f757-125">Konfiguriert grundlegende Netzwerkoptionen für <xref:System.Net> Klassen in den und verwandten untergeordneten Namespaces.</span><span class="sxs-lookup"><span data-stu-id="8f757-125">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="8f757-126">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="8f757-126">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="8f757-127">Gibt Module an, die zum Anfordern von Informationen von Internethosts verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8f757-127">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8f757-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8f757-128">Parent Elements</span></span>  
  
|<span data-ttu-id="8f757-129">**Element**</span><span class="sxs-lookup"><span data-stu-id="8f757-129">**Element**</span></span>|<span data-ttu-id="8f757-130">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="8f757-130">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8f757-131">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="8f757-131">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="8f757-132">Enthält Einstellungen für alle Namespaces.</span><span class="sxs-lookup"><span data-stu-id="8f757-132">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f757-133">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8f757-133">Remarks</span></span>  
 <span data-ttu-id="8f757-134">Das [ \<system.net>-Element](system-net-element-network-settings.md) enthält <xref:System.Net> Einstellungen für Klassen in den und verwandten untergeordneten Namespaces.</span><span class="sxs-lookup"><span data-stu-id="8f757-134">The [\<system.net>](system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="8f757-135">Die Einstellungen konfigurieren Authentifizierungsmodule, Verbindungsverwaltung, E-Mail-Einstellungen, den Proxyserver und Internetanforderungsmodule für den Empfang von Informationen von Internethosts.</span><span class="sxs-lookup"><span data-stu-id="8f757-135">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f757-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8f757-136">Example</span></span>  
 <span data-ttu-id="8f757-137">Das folgende Beispiel zeigt eine <xref:System.Net> typische Konfiguration, die von Klassen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8f757-137">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8f757-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8f757-138">See also</span></span>

- [<span data-ttu-id="8f757-139">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="8f757-139">Network Settings Schema</span></span>](index.md)
