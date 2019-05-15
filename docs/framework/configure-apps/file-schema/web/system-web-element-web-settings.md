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
ms.openlocfilehash: 3ffd25dae3826df0f02f2afb707f7317b2d92d24
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65584544"
---
# <a name="systemweb-element-web-settings"></a><span data-ttu-id="39a44-102">\<System.Web >-Element (Webeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="39a44-102">\<system.web> Element (Web Settings)</span></span>
<span data-ttu-id="39a44-103">Enthält Informationen dazu, wie die hostingebene von ASP.NET prozessübergreifende Verhalten verwaltet.</span><span class="sxs-lookup"><span data-stu-id="39a44-103">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
 <span data-ttu-id="39a44-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="39a44-104">\<configuration></span></span>  
<span data-ttu-id="39a44-105">\<System.Web >-Element (Webeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="39a44-105">\<system.web> Element (Web Settings)</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39a44-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="39a44-106">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39a44-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="39a44-107">Attributes and Elements</span></span>  
 <span data-ttu-id="39a44-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="39a44-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39a44-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="39a44-109">Attributes</span></span>  
 <span data-ttu-id="39a44-110">Keine</span><span class="sxs-lookup"><span data-stu-id="39a44-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="39a44-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="39a44-111">Child Elements</span></span>  
  
|<span data-ttu-id="39a44-112">Element</span><span class="sxs-lookup"><span data-stu-id="39a44-112">Element</span></span>|<span data-ttu-id="39a44-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39a44-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39a44-114">\<applicationPool></span><span class="sxs-lookup"><span data-stu-id="39a44-114">\<applicationPool></span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|<span data-ttu-id="39a44-115">Gibt Konfigurationseinstellungen für die IIS-Anwendungspools in eine Datei "aspnet.config" an.</span><span class="sxs-lookup"><span data-stu-id="39a44-115">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="39a44-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="39a44-116">Parent Elements</span></span>  
  
|<span data-ttu-id="39a44-117">Element</span><span class="sxs-lookup"><span data-stu-id="39a44-117">Element</span></span>|<span data-ttu-id="39a44-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39a44-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39a44-119">\<configuration></span><span class="sxs-lookup"><span data-stu-id="39a44-119">\<configuration></span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="39a44-120">Gibt das Stammelement in jeder Konfigurationsdatei an, die von der common Language Runtime und .NET Framework-Anwendungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="39a44-120">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39a44-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="39a44-121">Remarks</span></span>  
 <span data-ttu-id="39a44-122">Die `system.web` Element und dessen untergeordnete `applicationPool` Element wurden hinzugefügt, um .NET Framework als [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39a44-122">The `system.web` element and its child `applicationPool` element were added to the .NET Framework as of [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span></span> <span data-ttu-id="39a44-123">Beim Ausführen von [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] oder höher im integrierten Modus, diese Kombination von Element ermöglicht das Konfigurieren, wie ASP.NET Threads verwaltet, und wie diese Anforderungen Warteschlangen, wenn ASP.NET in einem IIS-Anwendungspool gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="39a44-123">When you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="39a44-124">Wenn das Ausführen [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] oder höhere Versionen im klassischen Bereitstellungsmodell oder ISAPI-Modus werden diese Einstellungen ignoriert.</span><span class="sxs-lookup"><span data-stu-id="39a44-124">If you run [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39a44-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="39a44-125">Example</span></span>  
 <span data-ttu-id="39a44-126">Das folgende Beispiel zeigt, wie Sie ASP.NET prozessübergreifende Verhalten in der Datei "aspnet.config" konfigurieren, wenn ASP.NET in einem IIS-Anwendungspool gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="39a44-126">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="39a44-127">Im Beispiel wird davon ausgegangen, dass IIS, im integrierten ausgeführt wird Modus und dass die Anwendung verwendet die [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] oder eine höhere Version.</span><span class="sxs-lookup"><span data-stu-id="39a44-127">The example assumes that IIS is running in Integrated mode and that the application is using the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] or a later version.</span></span> <span data-ttu-id="39a44-128">Dieses Verhalten tritt nicht in .NET Framework-Versionen älter als die [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="39a44-128">This behavior does not occur in versions of the .NET Framework earlier than the [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].</span></span> <span data-ttu-id="39a44-129">Die Werte im Beispiel werden die Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="39a44-129">The values in the example are the default values.</span></span>  
  
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
  
## <a name="element-information"></a><span data-ttu-id="39a44-130">Elementinformationen</span><span class="sxs-lookup"><span data-stu-id="39a44-130">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="39a44-131">Namespace</span><span class="sxs-lookup"><span data-stu-id="39a44-131">Namespace</span></span>||  
|<span data-ttu-id="39a44-132">Schemaname</span><span class="sxs-lookup"><span data-stu-id="39a44-132">Schema Name</span></span>||  
|<span data-ttu-id="39a44-133">Validierungsdatei</span><span class="sxs-lookup"><span data-stu-id="39a44-133">Validation File</span></span>||  
|<span data-ttu-id="39a44-134">Leer kann sein</span><span class="sxs-lookup"><span data-stu-id="39a44-134">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="39a44-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39a44-135">See also</span></span>

- [<span data-ttu-id="39a44-136">\<applicationPool>-Element (Webeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="39a44-136">\<applicationPool> Element (Web Settings)</span></span>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)
