---
title: '&lt;Entfernen Sie&gt; WebRequestModules (Network Settings)-Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- remove element, webRequestModules
- webRequestModules, remove element
- <remove> element, webRequestModules
- <webRequestModules>, remove element
ms.assetid: dd84d2fe-2f4f-457a-9d3c-441d0d21cc10
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: 391e5f2a7d9d8076ba9e9a3057e3d8899e2ce672
ms.sourcegitcommit: 15316053918995cc1380163a7d7e7edd5c44e6d7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2018
---
# <a name="ltremovegt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="8a577-102">&lt;Entfernen Sie&gt; WebRequestModules (Network Settings)-Element</span><span class="sxs-lookup"><span data-stu-id="8a577-102">&lt;remove&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="8a577-103">Entfernt ein benutzerdefiniertes Web-Request-Modul aus der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="8a577-103">Removes a custom Web request module from the application.</span></span>  
  
 <span data-ttu-id="8a577-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="8a577-104">\<configuration></span></span>  
<span data-ttu-id="8a577-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="8a577-105">\<system.net></span></span>  
<span data-ttu-id="8a577-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="8a577-106">\<webRequestModules></span></span>  
<span data-ttu-id="8a577-107">\<remove></span><span class="sxs-lookup"><span data-stu-id="8a577-107">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a577-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a577-108">Syntax</span></span>  
  
```xml  
<remove   
  prefix="URI prefix"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a577-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8a577-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8a577-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8a577-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a577-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="8a577-111">Attributes</span></span>  
  
|<span data-ttu-id="8a577-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="8a577-112">**Attribute**</span></span>|<span data-ttu-id="8a577-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="8a577-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`prefix`|<span data-ttu-id="8a577-114">Das URI-Präfix für Anforderungen, die von dieser Anforderung Webmodul behandelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8a577-114">The URI prefix for requests handled by this Web request module.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8a577-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8a577-115">Child Elements</span></span>  
 <span data-ttu-id="8a577-116">Keine</span><span class="sxs-lookup"><span data-stu-id="8a577-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8a577-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8a577-117">Parent Elements</span></span>  
  
|<span data-ttu-id="8a577-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="8a577-118">**Element**</span></span>|<span data-ttu-id="8a577-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="8a577-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8a577-120">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="8a577-120">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="8a577-121">Gibt die Module zu verwenden, um Informationen von Netzwerkhosts anfordern.</span><span class="sxs-lookup"><span data-stu-id="8a577-121">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a577-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8a577-122">Remarks</span></span>  
 <span data-ttu-id="8a577-123">Die `remove` -Element entfernt die registrierte Webmodul für die Anforderung für das angegebene URI-Präfix.</span><span class="sxs-lookup"><span data-stu-id="8a577-123">The `remove` element removes the registered Web request module for the specified URI prefix.</span></span>  
  
 <span data-ttu-id="8a577-124">Der Wert für die `prefix` Attribut muss die ersten Zeichen ein gültiger URI – z. B. "http", oder "http://www.contoso.com".</span><span class="sxs-lookup"><span data-stu-id="8a577-124">The value for the `prefix` attribute should be the leading characters of a valid URI -- for example, "http", or "http://www.contoso.com".</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8a577-125">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="8a577-125">Configuration Files</span></span>  
 <span data-ttu-id="8a577-126">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8a577-126">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a577-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8a577-127">Example</span></span>  
 <span data-ttu-id="8a577-128">Im folgenden Beispiel entfernt die vorhandene Anforderung Webmodul für HTTP und registriert dann ein neue benutzerdefiniertes Web Anforderung-Modul für HTTP-Anforderungen an www.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8a577-128">The following example removes the existing Web request module for HTTP and then registers a new custom Web request module for HTTP requests to www.contoso.com.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <remove prefix="http">  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a577-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a577-129">See Also</span></span>  
 <xref:System.Net.WebRequest>  
 [<span data-ttu-id="8a577-130">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="8a577-130">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
