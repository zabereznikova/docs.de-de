---
title: <system.web>-Element (Webeinstellungen)
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
ms.openlocfilehash: b37b05bdf90630251cbfcf86751243a3a8b77663
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152840"
---
# <a name="systemweb-element-web-settings"></a><span data-ttu-id="52c4a-102">\<system.web> Element (Webeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="52c4a-102">\<system.web> Element (Web Settings)</span></span>
<span data-ttu-id="52c4a-103">Enthält Informationen darüber, wie der ASP.NET Hosting-Layer das prozessweite Verhalten verwaltet.</span><span class="sxs-lookup"><span data-stu-id="52c4a-103">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
[<span data-ttu-id="52c4a-104">**\<Konfiguration>**</span><span class="sxs-lookup"><span data-stu-id="52c4a-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="52c4a-105">&nbsp;&nbsp;**\<system.web>**</span><span class="sxs-lookup"><span data-stu-id="52c4a-105">&nbsp;&nbsp;**\<system.web>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52c4a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="52c4a-106">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="52c4a-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="52c4a-107">Attributes and Elements</span></span>  

<span data-ttu-id="52c4a-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="52c4a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="52c4a-109">Attributes</span><span class="sxs-lookup"><span data-stu-id="52c4a-109">Attributes</span></span>  

<span data-ttu-id="52c4a-110">Keine.</span><span class="sxs-lookup"><span data-stu-id="52c4a-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="52c4a-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="52c4a-111">Child Elements</span></span>  
  
|<span data-ttu-id="52c4a-112">Element</span><span class="sxs-lookup"><span data-stu-id="52c4a-112">Element</span></span>|<span data-ttu-id="52c4a-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="52c4a-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52c4a-114">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="52c4a-114">\<applicationPool></span></span>](applicationpool-element-web-settings.md)|<span data-ttu-id="52c4a-115">Gibt Konfigurationseinstellungen für IIS-Anwendungspools in einer aspnet.config-Datei an.</span><span class="sxs-lookup"><span data-stu-id="52c4a-115">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="52c4a-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="52c4a-116">Parent Elements</span></span>  
  
|<span data-ttu-id="52c4a-117">Element</span><span class="sxs-lookup"><span data-stu-id="52c4a-117">Element</span></span>|<span data-ttu-id="52c4a-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="52c4a-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="52c4a-119">\<Konfiguration></span><span class="sxs-lookup"><span data-stu-id="52c4a-119">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="52c4a-120">Gibt das Stammelement in jeder Konfigurationsdatei an, die von der Common Language Runtime und .NET Framework-Anwendungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="52c4a-120">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52c4a-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="52c4a-121">Remarks</span></span>  

<span data-ttu-id="52c4a-122">Das `system.web` Element und `applicationPool` das untergeordnete Element wurden dem .NET Framework als .NET Framework 3.5 SP1 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="52c4a-122">The `system.web` element and its child `applicationPool` element were added to the .NET Framework as of .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="52c4a-123">Wenn Sie IIS 7.0 oder höher im integrierten Modus ausführen, können Sie mit dieser Elementkombination konfigurieren, wie ASP.NET Threads verwaltet und wie sie Anforderungen in die Warteschlange stellen, wenn ASP.NET in einem IIS-Anwendungspool gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="52c4a-123">When you run IIS 7.0 or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="52c4a-124">Wenn Sie IIS 7.0 oder neuere Versionen im Classic- oder ISAPI-Modus ausführen, werden diese Einstellungen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="52c4a-124">If you run IIS 7.0 or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52c4a-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="52c4a-125">Example</span></span>  

<span data-ttu-id="52c4a-126">Das folgende Beispiel zeigt, wie ASP.NET prozessweiten Verhalten in der Datei aspnet.config konfiguriert wird, wenn ASP.NET in einem IIS-Anwendungspool gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="52c4a-126">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="52c4a-127">Im Beispiel wird davon ausgegangen, dass IIS im integrierten Modus ausgeführt wird und dass die Anwendung .NET Framework 3.5 SP1 oder eine neuere Version verwendet.</span><span class="sxs-lookup"><span data-stu-id="52c4a-127">The example assumes that IIS is running in Integrated mode and that the application is using the .NET Framework 3.5 SP1 or a later version.</span></span> <span data-ttu-id="52c4a-128">Dieses Verhalten tritt nicht in Versionen von .NET Framework vor .NET Framework 3.5 SP1 auf.</span><span class="sxs-lookup"><span data-stu-id="52c4a-128">This behavior does not occur in versions of the .NET Framework earlier than the .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="52c4a-129">Die Werte im Beispiel sind die Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="52c4a-129">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="52c4a-130">Elementinformationen</span><span class="sxs-lookup"><span data-stu-id="52c4a-130">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="52c4a-131">Namespace</span><span class="sxs-lookup"><span data-stu-id="52c4a-131">Namespace</span></span>||  
|<span data-ttu-id="52c4a-132">Name des Schemas</span><span class="sxs-lookup"><span data-stu-id="52c4a-132">Schema Name</span></span>||  
|<span data-ttu-id="52c4a-133">Validierungsdatei</span><span class="sxs-lookup"><span data-stu-id="52c4a-133">Validation File</span></span>||  
|<span data-ttu-id="52c4a-134">Kann leer sein</span><span class="sxs-lookup"><span data-stu-id="52c4a-134">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="52c4a-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="52c4a-135">See also</span></span>

- [<span data-ttu-id="52c4a-136">\<applicationPool> Element (Webeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="52c4a-136">\<applicationPool> Element (Web Settings)</span></span>](applicationpool-element-web-settings.md)
