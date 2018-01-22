---
title: '&lt;Start&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
caps.latest.revision: "19"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 4299775cd23162839ab9846adc7d2c64cc18a404
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="ltstartupgt-element"></a><span data-ttu-id="b1de1-102">&lt;Start&gt; Element</span><span class="sxs-lookup"><span data-stu-id="b1de1-102">&lt;startup&gt; Element</span></span>
<span data-ttu-id="b1de1-103">Gibt die common Language Runtime-Startinformationen.</span><span class="sxs-lookup"><span data-stu-id="b1de1-103">Specifies common language runtime startup information.</span></span>  
  
 <span data-ttu-id="b1de1-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b1de1-104">\<configuration></span></span>  
<span data-ttu-id="b1de1-105">\<startup></span><span class="sxs-lookup"><span data-stu-id="b1de1-105">\<startup></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1de1-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b1de1-106">Syntax</span></span>  
  
```xml  
<startup useLegacyV2RuntimeActivationPolicy="true|false" >   
</startup>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b1de1-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b1de1-107">Attributes and Elements</span></span>  
 <span data-ttu-id="b1de1-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b1de1-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b1de1-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="b1de1-109">Attributes</span></span>  
  
|<span data-ttu-id="b1de1-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="b1de1-110">Attribute</span></span>|<span data-ttu-id="b1de1-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1de1-111">Description</span></span>|  
|---------------|-----------------|  
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="b1de1-112">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="b1de1-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b1de1-113">Gibt an, ob die [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] Runtime Aktivierungsrichtlinie oder zur Verwendung der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] Aktivierungsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="b1de1-113">Specifies whether to enable the [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] runtime activation policy or to use the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] activation policy.</span></span>|  
  
## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="b1de1-114">useLegacyV2RuntimeActivationPolicy-Attribut</span><span class="sxs-lookup"><span data-stu-id="b1de1-114">useLegacyV2RuntimeActivationPolicy Attribute</span></span>  
  
|<span data-ttu-id="b1de1-115">Wert</span><span class="sxs-lookup"><span data-stu-id="b1de1-115">Value</span></span>|<span data-ttu-id="b1de1-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1de1-116">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="b1de1-117">Aktivieren Sie [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] Aktivierung Laufzeitrichtlinie für die ausgewählte Runtime legacylaufzeit Aktivierung Techniken gebunden ist (z. B. der [CorBindToRuntimeEx-Funktion](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)) für die Laufzeit, die aus der Konfigurationsdatei anstelle von ausgewählt Capping diese auf CLR, Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="b1de1-117">Enable [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="b1de1-118">Wenn CLR-Version 4 oder höher aus der Konfigurationsdatei ausgewählt wird, werden im gemischten Modus Assemblys, die mit früheren Versionen von .NET Framework erstellt daher mit der ausgewählten Version der CLR geladen.</span><span class="sxs-lookup"><span data-stu-id="b1de1-118">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="b1de1-119">Wenn dieser Wert verhindert, dass CLR, Version 1.1 oder CLR, Version 2.0 Laden in den gleichen Prozess, die in-Process-Seite-an-Seite-Funktion effektiv deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b1de1-119">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|  
|`false`|<span data-ttu-id="b1de1-120">Verwenden Sie die Standardrichtlinie für die Aktivierung für die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] und später ist das ermöglichen legacylaufzeit Aktivierung Techniken, mit denen CLR, Version 1.1 oder 2.0 in den Prozess zu laden.</span><span class="sxs-lookup"><span data-stu-id="b1de1-120">Use the default activation policy for the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="b1de1-121">Das Festlegen dieses Werts wird verhindert, dass im gemischten Modus Assemblys vor dem Laden in .NET Framework 4 oder höher, es sei denn, sie mit .NET Framework 4 oder höher erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="b1de1-121">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="b1de1-122">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="b1de1-122">This value is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b1de1-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b1de1-123">Child Elements</span></span>  
  
|<span data-ttu-id="b1de1-124">Element</span><span class="sxs-lookup"><span data-stu-id="b1de1-124">Element</span></span>|<span data-ttu-id="b1de1-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1de1-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b1de1-126">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="b1de1-126">\<requiredRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|<span data-ttu-id="b1de1-127">Gibt an, dass die Anwendung nur Version 1.0 der Common Language Runtime unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b1de1-127">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="b1de1-128">Mit der Common Language Runtime-Version 1.1 oder höher entwickelte Anwendungen sollten verwenden die  **\<SupportedRuntime >** Element.</span><span class="sxs-lookup"><span data-stu-id="b1de1-128">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|  
|[<span data-ttu-id="b1de1-129">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="b1de1-129">\<supportedRuntime></span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|<span data-ttu-id="b1de1-130">Gibt an, welche Versionen der Common Language Runtime von der Anwendung unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="b1de1-130">Specifies which versions of the common language runtime the application supports.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b1de1-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b1de1-131">Parent Elements</span></span>  
  
|<span data-ttu-id="b1de1-132">Element</span><span class="sxs-lookup"><span data-stu-id="b1de1-132">Element</span></span>|<span data-ttu-id="b1de1-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1de1-133">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b1de1-134">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b1de1-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b1de1-135">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b1de1-135">Remarks</span></span>  
 <span data-ttu-id="b1de1-136">Die  **\<SupportedRuntime >** -Element sollte von allen Anwendungen, die mit Version 1.1 oder höher der Runtime erstellt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b1de1-136">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="b1de1-137">Anwendungen, die nur Version 1.0 der Laufzeit unterstützen müssen verwenden die  **\<RequiredRuntime >** Element.</span><span class="sxs-lookup"><span data-stu-id="b1de1-137">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>  
  
 <span data-ttu-id="b1de1-138">Der Startcode für eine in Microsoft Internet Explorer gehostete Anwendung ignoriert die  **\<Start >** Element und seine untergeordneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="b1de1-138">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>  
  
## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="b1de1-139">Das Attribut useLegacyV2RuntimeActivationPolicy</span><span class="sxs-lookup"><span data-stu-id="b1de1-139">The useLegacyV2RuntimeActivationPolicy Attribute</span></span>  
 <span data-ttu-id="b1de1-140">Dieses Attribut ist hilfreich, wenn Ihre Anwendung legacy-Aktivierungspfade,, wie z. B. verwendet die [CorBindToRuntimeEx-Funktion](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), und Sie möchten diese Pfade Version 4 der CLR anstelle von einer früheren Version aktivieren, oder wenn die Anwendung erstellt mit dem [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] , enthält jedoch eine Abhängigkeit auf eine im gemischten Modus-Assembly, die mit einer früheren Version von .NET Framework erstellt.</span><span class="sxs-lookup"><span data-stu-id="b1de1-140">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="b1de1-141">Legen Sie in jenen Szenarien kann das Attribut auf `true`.</span><span class="sxs-lookup"><span data-stu-id="b1de1-141">In those scenarios, set the attribute to `true`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b1de1-142">Wenn das Attribut auf `true` verhindert CLR, Version 1.1 oder CLR, Version 2.0 lädt in den gleichen Prozess, die in-Process-Seite-an-Seite-Funktion effektiv deaktiviert (finden Sie unter [Side-by-Side-Ausführung für COM-Interop](http://msdn.microsoft.com/library/4302318c-3586-49bf-8620-b9a39cdf4a32)).</span><span class="sxs-lookup"><span data-stu-id="b1de1-142">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](http://msdn.microsoft.com/library/4302318c-3586-49bf-8620-b9a39cdf4a32)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1de1-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b1de1-143">Example</span></span>  
 <span data-ttu-id="b1de1-144">Im folgende Beispiel wird gezeigt, wie die Common Language Runtime-Version in einer Konfigurationsdatei angegeben.</span><span class="sxs-lookup"><span data-stu-id="b1de1-144">The following example shows how to specify the runtime version in a configuration file.</span></span>  
  
```xml  
<!-- When used with version 1.0 of the .NET Framework runtime -->  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
<!-- When used with version 1.1 (or later) of the runtime -->  
<configuration>  
   <startup>  
      <supportedRuntime version="v1.1.4322"/>  
      <supportedRuntime version="v1.0.3705"/>  
   </startup>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b1de1-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1de1-145">See Also</span></span>  
 [<span data-ttu-id="b1de1-146">Startup Settings Schema (Schema für Starteinstellungen)</span><span class="sxs-lookup"><span data-stu-id="b1de1-146">Startup Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [<span data-ttu-id="b1de1-147">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="b1de1-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="b1de1-148">\<PaveOver> Specifying Which Runtime Version to Use (Festlegen der zu verwendenden Runtimeversion)</span><span class="sxs-lookup"><span data-stu-id="b1de1-148">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](http://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)  
 [<span data-ttu-id="b1de1-149">Seite-an-Seite-Ausführung für COM-Interop</span><span class="sxs-lookup"><span data-stu-id="b1de1-149">Side-by-Side Execution for COM Interop</span></span>](http://msdn.microsoft.com/library/4302318c-3586-49bf-8620-b9a39cdf4a32)  
 [<span data-ttu-id="b1de1-150">Prozessinterne parallele Ausführung</span><span class="sxs-lookup"><span data-stu-id="b1de1-150">In-Process Side-by-Side Execution</span></span>](../../../../../docs/framework/deployment/in-process-side-by-side-execution.md)
