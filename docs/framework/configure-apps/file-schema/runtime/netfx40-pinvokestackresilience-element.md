---
title: '&lt;NetFx40_PInvokeStackResilience&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b17816ee6134dc6b3074256093c0cba07419baf5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltnetfx40pinvokestackresiliencegt-element"></a><span data-ttu-id="96465-102">&lt;NetFx40_PInvokeStackResilience&gt; Element</span><span class="sxs-lookup"><span data-stu-id="96465-102">&lt;NetFx40_PInvokeStackResilience&gt; Element</span></span>
<span data-ttu-id="96465-103">Gibt an, ob die Runtime falsche Plattformaufrufdeklarationen zur Laufzeit automatisch korrigiert. Dies führt zu langsameren Übergängen zwischen verwaltetem und nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="96465-103">Specifies whether the runtime automatically fixes incorrect platform invoke declarations at run time, at the cost of slower transitions between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="96465-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="96465-104">\<configuration></span></span>  
<span data-ttu-id="96465-105">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="96465-105">\<runtime></span></span>  
<span data-ttu-id="96465-106">< NetFx40_PInvokeStackResilience ></span><span class="sxs-lookup"><span data-stu-id="96465-106"><NetFx40_PInvokeStackResilience></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96465-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="96465-107">Syntax</span></span>  
  
```xml  
<NetFx40_PInvokeStackResilience  enabled="1|0"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="96465-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="96465-108">Attributes and Elements</span></span>  
 <span data-ttu-id="96465-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="96465-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="96465-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="96465-110">Attributes</span></span>  
  
|<span data-ttu-id="96465-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="96465-111">Attribute</span></span>|<span data-ttu-id="96465-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="96465-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="96465-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="96465-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="96465-114">Gibt an, ob die Laufzeit falsche Plattform erkennt Plattformaufrufdeklarationen und behebt den Stapel automatisch zur Laufzeit auf 32-Bit-Plattformen.</span><span class="sxs-lookup"><span data-stu-id="96465-114">Specifies whether the runtime detects incorrect platform invoke declarations and automatically fixes the stack at run time on 32-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="96465-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="96465-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="96465-116">Wert</span><span class="sxs-lookup"><span data-stu-id="96465-116">Value</span></span>|<span data-ttu-id="96465-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="96465-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="96465-118">Die Common Language Runtime verwendet schnellere Interop-Marshalling-Architektur eingeführt, die der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], die nicht erkannt und Updates falscher Plattformaufrufdeklarationen.</span><span class="sxs-lookup"><span data-stu-id="96465-118">The runtime uses the faster interop marshaling architecture introduced in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], which does not detect and fix incorrect platform invoke declarations.</span></span> <span data-ttu-id="96465-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="96465-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="96465-120">Die Common Language Runtime verwendet langsamer Übergänge, die erkennt und korrigiert falsche Plattform Plattformaufrufdeklarationen.</span><span class="sxs-lookup"><span data-stu-id="96465-120">The runtime uses slower transitions that detect and fix incorrect platform invoke declarations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="96465-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="96465-121">Child Elements</span></span>  
 <span data-ttu-id="96465-122">Keine</span><span class="sxs-lookup"><span data-stu-id="96465-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="96465-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="96465-123">Parent Elements</span></span>  
  
|<span data-ttu-id="96465-124">Element</span><span class="sxs-lookup"><span data-stu-id="96465-124">Element</span></span>|<span data-ttu-id="96465-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="96465-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="96465-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="96465-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="96465-127">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="96465-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96465-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="96465-128">Remarks</span></span>  
 <span data-ttu-id="96465-129">Dieses Element können Sie schneller Interop-Marshalling für Laufzeit-robusten Schutz vor falsche Plattform Plattformaufrufdeklarationen abwägen.</span><span class="sxs-lookup"><span data-stu-id="96465-129">This element enables you to trade faster interop marshaling for run-time resilience against incorrect platform invoke declarations.</span></span>  
  
 <span data-ttu-id="96465-130">Beginnend mit der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], eine optimierte Interop-Marshalling-Architektur bietet eine deutliche leistungsverbesserung für Übergänge von verwaltetem Code an nicht verwalteten Code.</span><span class="sxs-lookup"><span data-stu-id="96465-130">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], a streamlined interop marshaling architecture provides a significant performance improvement for transitions from managed code to unmanaged code.</span></span> <span data-ttu-id="96465-131">In früheren Versionen von .NET Framework die Marshalling Ebene erkannt falsche Plattformaufrufmethode Deklarationen auf 32-Bit-Plattformen und den Stapel automatisch korrigiert.</span><span class="sxs-lookup"><span data-stu-id="96465-131">In earlier versions of the .NET Framework, the marshaling layer detected incorrect platform invoke declarations on 32-bit platforms and automatically fixed the stack.</span></span> <span data-ttu-id="96465-132">Die neue Architektur Marshalling entfällt dieser Schritt.</span><span class="sxs-lookup"><span data-stu-id="96465-132">The new marshaling architecture eliminates this step.</span></span> <span data-ttu-id="96465-133">Daher sind Übergänge sehr schnell, aber eine falsche Plattformaufruf Deklaration können einen Anwendung Fehler verursachen.</span><span class="sxs-lookup"><span data-stu-id="96465-133">As a result, transitions are very fast, but an incorrect platform invoke declaration can cause a program failure.</span></span>  
  
 <span data-ttu-id="96465-134">Um während der Entwicklung falsche Deklarationen erkennen zu erleichtern, wurde die Visual Studio debuggen verbessert.</span><span class="sxs-lookup"><span data-stu-id="96465-134">To make it easy to detect incorrect declarations during development, the Visual Studio debugging experience has been improved.</span></span> <span data-ttu-id="96465-135">Die [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) Assistent für verwaltetes Debuggen (MDA) benachrichtigt Sie falsche Plattform Deklarationen aufgerufen wird, wenn Ihre Anwendung mit dem angefügten Debugger ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="96465-135">The [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) managed debugging assistant (MDA) notifies you of incorrect platform invoke declarations when your application is running with the debugger attached.</span></span>  
  
 <span data-ttu-id="96465-136">Adresse Szenarien, in denen Ihre Anwendung Komponenten verwendet, die nicht neu kompilieren und, dass wurden falsche Plattformaufrufdeklarationen, Sie können, die `NetFx40_PInvokeStackResilience` Element.</span><span class="sxs-lookup"><span data-stu-id="96465-136">To address scenarios where your application uses components that you cannot recompile, and that have incorrect platform invoke declarations, you can use the `NetFx40_PInvokeStackResilience` element.</span></span> <span data-ttu-id="96465-137">Die Konfigurationsdatei der Anwendung mit diesem Element hinzugefügt `enabled="1"` "OPTS" in einem Kompatibilitätsmodus mit dem Verhalten früherer Versionen von .NET Framework, allerdings zum Preis einer langsameren Übergängen.</span><span class="sxs-lookup"><span data-stu-id="96465-137">Adding this element to your application configuration file with `enabled="1"` opts into a compatibility mode with the behavior of earlier versions of the .NET Framework, at the cost of slower transitions.</span></span> <span data-ttu-id="96465-138">Assemblys, die auf früheren Versionen von .NET Framework kompiliert wurden diesem Kompatibilitätsmodus werden automatisch festgelegt, und dieses Element ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="96465-138">Assemblies that have been compiled against earlier versions of the .NET Framework are automatically opted into this compatibility mode, and do not need this element.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="96465-139">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="96465-139">Configuration File</span></span>  
 <span data-ttu-id="96465-140">Dieses Element kann nur in der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="96465-140">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96465-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="96465-141">Example</span></span>  
 <span data-ttu-id="96465-142">Im folgenden Beispiel gezeigt ist wie erhöhte Stabilität gegen falsche aktiviert Plattformaufrufdeklarationen für eine Anwendung, allerdings zum Preis einer langsameren Übergänge zwischen verwalteten und nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="96465-142">The following example shows how to opt into increased resilience against incorrect platform invoke declarations for an application, at the cost of slower transitions between managed and unmanaged code.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_PInvokeStackResilience enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="96465-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96465-143">See Also</span></span>  
 [<span data-ttu-id="96465-144">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="96465-144">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="96465-145">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="96465-145">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="96465-146">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="96465-146">pInvokeStackImbalance</span></span>](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)
