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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154555"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="2f5cc-102">\<system.Net>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="2f5cc-102">\<system.Net> Element (Network Settings)</span></span>
<span data-ttu-id="2f5cc-103">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2f5cc-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.net>**  
  
## <a name="syntax"></a><span data-ttu-id="2f5cc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2f5cc-104">Syntax</span></span>  
  
```xml  
<system.net>
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f5cc-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2f5cc-105">Attributes and Elements</span></span>  
 <span data-ttu-id="2f5cc-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2f5cc-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f5cc-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="2f5cc-107">Attributes</span></span>  
 <span data-ttu-id="2f5cc-108">Keine</span><span class="sxs-lookup"><span data-stu-id="2f5cc-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="2f5cc-109">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2f5cc-109">Child Elements</span></span>  
  
|<span data-ttu-id="2f5cc-110">**Element**</span><span class="sxs-lookup"><span data-stu-id="2f5cc-110">**Element**</span></span>|<span data-ttu-id="2f5cc-111">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2f5cc-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2f5cc-112">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="2f5cc-112">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="2f5cc-113">Gibt Module an, die zum Authentifizieren von Internet Anforderungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2f5cc-113">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="2f5cc-114">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="2f5cc-114">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="2f5cc-115">Gibt die maximale Anzahl von Verbindungen mit einem Internet Host an.</span><span class="sxs-lookup"><span data-stu-id="2f5cc-115">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="2f5cc-116">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="2f5cc-116">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="2f5cc-117">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="2f5cc-117">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="2f5cc-118">mailSettings</span><span class="sxs-lookup"><span data-stu-id="2f5cc-118">mailSettings</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="2f5cc-119">Konfiguriert SMTP (Simple Mail Transport Protocol)-e-Mail-Sende Optionen.</span><span class="sxs-lookup"><span data-stu-id="2f5cc-119">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="2f5cc-120">requestCaching</span><span class="sxs-lookup"><span data-stu-id="2f5cc-120">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="2f5cc-121">Steuert den zwischen Speicherungs Mechanismus für Netzwerk Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="2f5cc-121">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="2f5cc-122">settings</span><span class="sxs-lookup"><span data-stu-id="2f5cc-122">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="2f5cc-123">Konfiguriert grundlegende Netzwerkoptionen für Klassen in den <xref:System.Net> zugehörigen untergeordneten Namespaces.</span><span class="sxs-lookup"><span data-stu-id="2f5cc-123">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="2f5cc-124">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="2f5cc-124">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="2f5cc-125">Gibt Module an, die zum Anfordern von Informationen von Internet Hosts verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2f5cc-125">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2f5cc-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2f5cc-126">Parent Elements</span></span>  
  
|<span data-ttu-id="2f5cc-127">**Element**</span><span class="sxs-lookup"><span data-stu-id="2f5cc-127">**Element**</span></span>|<span data-ttu-id="2f5cc-128">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="2f5cc-128">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="2f5cc-129">configuration</span><span class="sxs-lookup"><span data-stu-id="2f5cc-129">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="2f5cc-130">Enthält Einstellungen für alle Namespaces.</span><span class="sxs-lookup"><span data-stu-id="2f5cc-130">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f5cc-131">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2f5cc-131">Remarks</span></span>  
 <span data-ttu-id="2f5cc-132">Das [\<system.net>](system-net-element-network-settings.md) -Element enthält Einstellungen für Klassen in den zugehörigen untergeordneten <xref:System.Net> Namespaces.</span><span class="sxs-lookup"><span data-stu-id="2f5cc-132">The [\<system.net>](system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="2f5cc-133">Die Einstellungen konfigurieren Authentifizierungs Module, Verbindungs Verwaltung, e-Mail-Einstellungen, den Proxy Server und Internet Anforderungs Module zum Empfangen von Informationen von Internet Hosts.</span><span class="sxs-lookup"><span data-stu-id="2f5cc-133">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f5cc-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2f5cc-134">Example</span></span>  
 <span data-ttu-id="2f5cc-135">Das folgende Beispiel zeigt eine typische Konfiguration, die von-Klassen verwendet wird <xref:System.Net> .</span><span class="sxs-lookup"><span data-stu-id="2f5cc-135">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2f5cc-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2f5cc-136">See also</span></span>

- [<span data-ttu-id="2f5cc-137">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="2f5cc-137">Network Settings Schema</span></span>](index.md)
