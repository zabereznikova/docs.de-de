---
title: '&lt;Deaktivieren Sie&gt; -Element für WebRequestModules (Netzwerkeinstellungen)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/webRequestModules/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- <clear> element, webRequestModules
- <webRequestModules>, clear element
- webRequestModules, clear element
- clear element, webRequestModules
ms.assetid: 48f38bcb-f30c-4b74-a8f0-1a3caf1aa96f
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 2b313aa2481b1257715ac4dbc6d452e2120f4726
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2018
ms.locfileid: "47425915"
---
# <a name="ltcleargt-element-for-webrequestmodules-network-settings"></a><span data-ttu-id="a8a3a-102">&lt;Deaktivieren Sie&gt; -Element für WebRequestModules (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a8a3a-102">&lt;clear&gt; Element for webRequestModules (Network Settings)</span></span>
<span data-ttu-id="a8a3a-103">Entfernt alle registrierte Webanforderungsmodulen aus der Anwendung an.</span><span class="sxs-lookup"><span data-stu-id="a8a3a-103">Removes all registered Web request modules from the application.</span></span>  
  
 <span data-ttu-id="a8a3a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a8a3a-104">\<configuration></span></span>  
<span data-ttu-id="a8a3a-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="a8a3a-105">\<system.net></span></span>  
<span data-ttu-id="a8a3a-106">\<webRequestModules></span><span class="sxs-lookup"><span data-stu-id="a8a3a-106">\<webRequestModules></span></span>  
<span data-ttu-id="a8a3a-107">\<Deaktivieren Sie ></span><span class="sxs-lookup"><span data-stu-id="a8a3a-107">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8a3a-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="a8a3a-108">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a8a3a-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a8a3a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a8a3a-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a8a3a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a8a3a-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="a8a3a-111">Attributes</span></span>  
 <span data-ttu-id="a8a3a-112">Keine</span><span class="sxs-lookup"><span data-stu-id="a8a3a-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a8a3a-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a8a3a-113">Child Elements</span></span>  
 <span data-ttu-id="a8a3a-114">Keine</span><span class="sxs-lookup"><span data-stu-id="a8a3a-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a8a3a-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a8a3a-115">Parent Elements</span></span>  
  
|<span data-ttu-id="a8a3a-116">**Element**</span><span class="sxs-lookup"><span data-stu-id="a8a3a-116">**Element**</span></span>|<span data-ttu-id="a8a3a-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a8a3a-117">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="a8a3a-118">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="a8a3a-118">webRequestModules</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|<span data-ttu-id="a8a3a-119">Gibt die Module zu verwenden, um Informationen aus der Hosts im Netzwerk anzufordern.</span><span class="sxs-lookup"><span data-stu-id="a8a3a-119">Specifies modules to use to request information from network hosts.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8a3a-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a8a3a-120">Remarks</span></span>  
 <span data-ttu-id="a8a3a-121">Die `clear` -Element entfernt alle registrierte Webanforderungsmodulen, die weiter oben in der Konfigurationsdatei oder auf einer höheren Ebene in der Konfigurationshierarchie definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="a8a3a-121">The `clear` element removes all registered Web request modules that were defined earlier in the configuration file or at a higher level in the configuration hierarchy.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="a8a3a-122">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="a8a3a-122">Configuration Files</span></span>  
 <span data-ttu-id="a8a3a-123">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a8a3a-123">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8a3a-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a8a3a-124">Example</span></span>  
 <span data-ttu-id="a8a3a-125">Das folgende Beispiel löscht alle Webanforderungsmodule und registriert anschließend ein Webanforderungsmodul für HTTP.</span><span class="sxs-lookup"><span data-stu-id="a8a3a-125">The following example clears all Web request modules and then registers a Web request module for HTTP.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a8a3a-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8a3a-126">See Also</span></span>  
 <xref:System.Net.WebRequest>  
 [<span data-ttu-id="a8a3a-127">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="a8a3a-127">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
