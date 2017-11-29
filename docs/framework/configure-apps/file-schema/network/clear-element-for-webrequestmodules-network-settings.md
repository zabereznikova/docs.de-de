---
title: '&lt;Deaktivieren Sie&gt; WebRequestModules (Network Settings)-Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, webRequestModules
- <webRequestModules>, clear element
- webRequestModules, clear element
- clear element, webRequestModules
ms.assetid: 48f38bcb-f30c-4b74-a8f0-1a3caf1aa96f
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: c88792663b07ace7250b6ee4065e60d6cfb90afd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltcleargt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="e031a-102">&lt;Deaktivieren Sie&gt; WebRequestModules (Network Settings)-Element</span><span class="sxs-lookup"><span data-stu-id="e031a-102">&lt;clear&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="e031a-103">Entfernt alle registrierten Anforderung Webmodule aus der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="e031a-103">Removes all registered Web request modules from the application.</span></span>  
  
 <span data-ttu-id="e031a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e031a-104">\<configuration></span></span>  
<span data-ttu-id="e031a-105">\<System.NET ></span><span class="sxs-lookup"><span data-stu-id="e031a-105">\<system.net></span></span>  
<span data-ttu-id="e031a-106">\<WebRequestModules ></span><span class="sxs-lookup"><span data-stu-id="e031a-106">\<webRequestModules></span></span>  
<span data-ttu-id="e031a-107">\<Deaktivieren Sie ></span><span class="sxs-lookup"><span data-stu-id="e031a-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e031a-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="e031a-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e031a-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e031a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e031a-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e031a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e031a-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="e031a-111">Attributes</span></span>  
 <span data-ttu-id="e031a-112">Keine.</span><span class="sxs-lookup"><span data-stu-id="e031a-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e031a-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e031a-113">Child Elements</span></span>  
 <span data-ttu-id="e031a-114">Keine</span><span class="sxs-lookup"><span data-stu-id="e031a-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e031a-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e031a-115">Parent Elements</span></span>  
  
|<span data-ttu-id="e031a-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="e031a-116">**Element**</span></span>|<span data-ttu-id="e031a-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="e031a-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="e031a-118">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="e031a-118">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="e031a-119">Gibt die Module zu verwenden, um Informationen von Netzwerkhosts anfordern.</span><span class="sxs-lookup"><span data-stu-id="e031a-119">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e031a-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e031a-120">Remarks</span></span>  
 <span data-ttu-id="e031a-121">Die `clear` -Element entfernt alle registrierten Anforderung Webmodule, die weiter oben in der Konfigurationsdatei oder auf einer höheren Ebene in der Konfigurationshierarchie definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e031a-121">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="e031a-122">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="e031a-122">Configuration Files</span></span>  
 <span data-ttu-id="e031a-123">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e031a-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e031a-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e031a-124">Example</span></span>  
 <span data-ttu-id="e031a-125">Im folgenden Beispiel löscht alle Anforderung Webmodule und registriert dann eine Anforderung Webmodul für HTTP.</span><span class="sxs-lookup"><span data-stu-id="e031a-125">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <webRequestModules>  
      <clear/>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator, System, Version=2.0.3600.0,  
           Culture=neutral, PublicKeyToken=b77a5c561934e089"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e031a-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e031a-126">See Also</span></span>  
 <xref:System.Net.WebRequest>  
 [<span data-ttu-id="e031a-127">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="e031a-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
