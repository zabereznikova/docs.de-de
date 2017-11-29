---
title: '&lt;System.Web&gt; Element (Webeinstellungen)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 44a978eae9ae85e1ba12f117288a3c9ce4db75b4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="ltsystemwebgt-element-web-settings"></a><span data-ttu-id="0d07b-102">&lt;System.Web&gt; Element (Webeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="0d07b-102">&lt;system.web&gt; Element (Web Settings)</span></span>
<span data-ttu-id="0d07b-103">Enthält Informationen dazu, wie die Hostebene ASP.NET prozessübergreifende Verhalten verwaltet.</span><span class="sxs-lookup"><span data-stu-id="0d07b-103">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
 <span data-ttu-id="0d07b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0d07b-104">\<configuration></span></span>  
<span data-ttu-id="0d07b-105">\<System.Web >-Element (Webeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="0d07b-105">\<system.web> Element (Web Settings)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d07b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="0d07b-106">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d07b-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0d07b-107">Attributes and Elements</span></span>  
 <span data-ttu-id="0d07b-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0d07b-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d07b-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="0d07b-109">Attributes</span></span>  
 <span data-ttu-id="0d07b-110">Keine.</span><span class="sxs-lookup"><span data-stu-id="0d07b-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0d07b-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0d07b-111">Child Elements</span></span>  
  
|<span data-ttu-id="0d07b-112">Element</span><span class="sxs-lookup"><span data-stu-id="0d07b-112">Element</span></span>|<span data-ttu-id="0d07b-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0d07b-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0d07b-114">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="0d07b-114">\<applicationPool></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|<span data-ttu-id="0d07b-115">Gibt Konfigurationseinstellungen für IIS-Anwendungspools in aspnet.config-Datei an.</span><span class="sxs-lookup"><span data-stu-id="0d07b-115">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0d07b-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0d07b-116">Parent Elements</span></span>  
  
|<span data-ttu-id="0d07b-117">Element</span><span class="sxs-lookup"><span data-stu-id="0d07b-117">Element</span></span>|<span data-ttu-id="0d07b-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0d07b-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0d07b-119">\<configuration></span><span class="sxs-lookup"><span data-stu-id="0d07b-119">\<configuration></span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="0d07b-120">Gibt das Stammelement in jeder Konfigurationsdatei an, die von der Common Language Runtime und den [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] -Anwendungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0d07b-120">Specifies the root element in every configuration file that is used by the common language runtime and [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d07b-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0d07b-121">Remarks</span></span>  
 <span data-ttu-id="0d07b-122">Die `system.web` -Elements und seines untergeordneten `applicationPool` Element wurden hinzugefügt, um die [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] ab [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d07b-122">The `system.web` element and its child `applicationPool` element were added to the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] as of [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span></span> <span data-ttu-id="0d07b-123">Bei der Ausführung [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] oder höheren Versionen im integrierten Modus Kombination aus diesem Element können Sie konfigurieren, wie diese Anforderungen Warteschlange, wenn ASP.NET in einem IIS-Anwendungspool gehostet wird und wie ASP.NET Threads verwaltet.</span><span class="sxs-lookup"><span data-stu-id="0d07b-123">When you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="0d07b-124">Wenn das Ausführen [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] oder höheren Versionen im klassischen Modus oder den ISAPI-Modus, werden diese Einstellungen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="0d07b-124">If you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d07b-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0d07b-125">Example</span></span>  
 <span data-ttu-id="0d07b-126">Das folgende Beispiel zeigt, wie ASP.NET prozessübergreifende Verhalten in aspnet.config-Datei konfigurieren, wenn ASP.NET in einem IIS-Anwendungspool gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="0d07b-126">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="0d07b-127">Im Beispiel wird davon ausgegangen, dass IIS, im integrierten ausgeführt wird Modus und, dass die Anwendung verwendet die [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] oder eine höhere Version.</span><span class="sxs-lookup"><span data-stu-id="0d07b-127">The example assumes that IIS is running in Integrated mode and that the application is using the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] or a later version.</span></span> <span data-ttu-id="0d07b-128">Dieses Verhalten tritt nicht in Versionen von der [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] älter als die [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d07b-128">This behavior does not occur in versions of the [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] earlier than the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span></span> <span data-ttu-id="0d07b-129">Die Werte im Beispiel sind die Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="0d07b-129">The values in the example are the default values.</span></span>  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool   
        maxConcurrentRequestsPerCPU="5000"   
        maxConcurrentThreadsPerCPU="0"   
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="0d07b-130">Elementinformationen</span><span class="sxs-lookup"><span data-stu-id="0d07b-130">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0d07b-131">Namespace</span><span class="sxs-lookup"><span data-stu-id="0d07b-131">Namespace</span></span>||  
|<span data-ttu-id="0d07b-132">Schemaname</span><span class="sxs-lookup"><span data-stu-id="0d07b-132">Schema Name</span></span>||  
|<span data-ttu-id="0d07b-133">Validierungsdatei</span><span class="sxs-lookup"><span data-stu-id="0d07b-133">Validation File</span></span>||  
|<span data-ttu-id="0d07b-134">Leer kann sein</span><span class="sxs-lookup"><span data-stu-id="0d07b-134">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="0d07b-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d07b-135">See Also</span></span>  
 [<span data-ttu-id="0d07b-136">\<applicationPool>-Element (Webeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="0d07b-136">\<applicationPool> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)
