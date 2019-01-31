---
title: < NetFx40_PInvokeStackResilience >-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8bc0d7c9222c31900cad9a8be05c79f7f8a04719
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55289340"
---
# <a name="netfx40pinvokestackresilience-element"></a><span data-ttu-id="e2877-102">\<NetFx40_PInvokeStackResilience >-Element</span><span class="sxs-lookup"><span data-stu-id="e2877-102">\<NetFx40_PInvokeStackResilience> Element</span></span>
<span data-ttu-id="e2877-103">Gibt an, ob die Runtime falsche Plattformaufrufdeklarationen zur Laufzeit automatisch korrigiert. Dies führt zu langsameren Übergängen zwischen verwaltetem und nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="e2877-103">Specifies whether the runtime automatically fixes incorrect platform invoke declarations at run time, at the cost of slower transitions between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="e2877-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e2877-104">\<configuration></span></span>  
<span data-ttu-id="e2877-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="e2877-105">\<runtime></span></span>  
<span data-ttu-id="e2877-106"><NetFx40_PInvokeStackResilience></span><span class="sxs-lookup"><span data-stu-id="e2877-106"><NetFx40_PInvokeStackResilience></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2877-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2877-107">Syntax</span></span>  
  
```xml  
<NetFx40_PInvokeStackResilience  enabled="1|0"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2877-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e2877-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e2877-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e2877-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2877-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="e2877-110">Attributes</span></span>  
  
|<span data-ttu-id="e2877-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="e2877-111">Attribute</span></span>|<span data-ttu-id="e2877-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e2877-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="e2877-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="e2877-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="e2877-114">Gibt an, ob die Runtime falsche Plattformaufrufdeklarationen erkennt Deklarationen und behebt automatisch auf 32-Bit-Plattformen zur Laufzeit den Stapel.</span><span class="sxs-lookup"><span data-stu-id="e2877-114">Specifies whether the runtime detects incorrect platform invoke declarations and automatically fixes the stack at run time on 32-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="e2877-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="e2877-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="e2877-116">Wert</span><span class="sxs-lookup"><span data-stu-id="e2877-116">Value</span></span>|<span data-ttu-id="e2877-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e2877-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="e2877-118">Die Common Language Runtime verwendet schneller Interop-Marshalling-Architektur eingeführt, die der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], die nicht erkannt und Korrektur falsche Plattformaufrufdeklarationen.</span><span class="sxs-lookup"><span data-stu-id="e2877-118">The runtime uses the faster interop marshaling architecture introduced in the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], which does not detect and fix incorrect platform invoke declarations.</span></span> <span data-ttu-id="e2877-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="e2877-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="e2877-120">Die Common Language Runtime verwendet langsameren Übergängen, die Erkennung und Behebung fehlerhafter Plattformaufrufdeklarationen.</span><span class="sxs-lookup"><span data-stu-id="e2877-120">The runtime uses slower transitions that detect and fix incorrect platform invoke declarations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e2877-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e2877-121">Child Elements</span></span>  
 <span data-ttu-id="e2877-122">Keine</span><span class="sxs-lookup"><span data-stu-id="e2877-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e2877-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e2877-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e2877-124">Element</span><span class="sxs-lookup"><span data-stu-id="e2877-124">Element</span></span>|<span data-ttu-id="e2877-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e2877-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e2877-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e2877-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e2877-127">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="e2877-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2877-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e2877-128">Remarks</span></span>  
 <span data-ttu-id="e2877-129">Dieses Element können Sie eine Abstimmung zwischen schneller interop-Marshalling für Laufzeit resilienz gegen fehlerhafter Plattformaufruf Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="e2877-129">This element enables you to trade faster interop marshaling for run-time resilience against incorrect platform invoke declarations.</span></span>  
  
 <span data-ttu-id="e2877-130">Beginnend mit der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], eine optimierte Interop-Marshalling-Architektur bietet eine deutliche leistungsverbesserung für Übergänge von verwaltetem Code an nicht verwalteten Code.</span><span class="sxs-lookup"><span data-stu-id="e2877-130">Starting with the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], a streamlined interop marshaling architecture provides a significant performance improvement for transitions from managed code to unmanaged code.</span></span> <span data-ttu-id="e2877-131">In früheren Versionen von .NET Framework das Marshalling Ebene erkannt falsch Plattformaufrufmethode Deklarationen auf 32-Bit-Plattformen und automatisch korrigiert den Stapel.</span><span class="sxs-lookup"><span data-stu-id="e2877-131">In earlier versions of the .NET Framework, the marshaling layer detected incorrect platform invoke declarations on 32-bit platforms and automatically fixed the stack.</span></span> <span data-ttu-id="e2877-132">Die neue Architektur für Marshalling entfällt dieser Schritt.</span><span class="sxs-lookup"><span data-stu-id="e2877-132">The new marshaling architecture eliminates this step.</span></span> <span data-ttu-id="e2877-133">Daher sind Übergänge sehr schnell, aber es wird eine falsche Plattform aufrufen Deklaration einen Programmfehler verursachen können.</span><span class="sxs-lookup"><span data-stu-id="e2877-133">As a result, transitions are very fast, but an incorrect platform invoke declaration can cause a program failure.</span></span>  
  
 <span data-ttu-id="e2877-134">Um falsche Deklarationen zu erkennen, während der Entwicklung zu erleichtern, wurde der Visual Studio-Debuggingumgebung verbessert.</span><span class="sxs-lookup"><span data-stu-id="e2877-134">To make it easy to detect incorrect declarations during development, the Visual Studio debugging experience has been improved.</span></span> <span data-ttu-id="e2877-135">Die [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) -Assistent für verwaltetes Debuggens (MDA) informiert Sie über falschen Deklarationen aufrufen, wenn Ihre Anwendung mit dem angefügten Debugger ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e2877-135">The [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) managed debugging assistant (MDA) notifies you of incorrect platform invoke declarations when your application is running with the debugger attached.</span></span>  
  
 <span data-ttu-id="e2877-136">Szenarien, in denen Ihre Anwendung Komponenten verwendet, die Sie nicht neu kompilieren, und haben falsche Plattformaufrufdeklarationen, können Sie verwenden, die `NetFx40_PInvokeStackResilience` Element.</span><span class="sxs-lookup"><span data-stu-id="e2877-136">To address scenarios where your application uses components that you cannot recompile, and that have incorrect platform invoke declarations, you can use the `NetFx40_PInvokeStackResilience` element.</span></span> <span data-ttu-id="e2877-137">Die Konfigurationsdatei der Anwendung mit diesem Element hinzugefügt `enabled="1"` "OPTS" in einem Kompatibilitätsmodus, mit dem Verhalten früherer Versionen von .NET Framework, was zu langsameren Übergängen.</span><span class="sxs-lookup"><span data-stu-id="e2877-137">Adding this element to your application configuration file with `enabled="1"` opts into a compatibility mode with the behavior of earlier versions of the .NET Framework, at the cost of slower transitions.</span></span> <span data-ttu-id="e2877-138">Assemblys, die auf früheren Versionen von .NET Framework kompiliert wurden, werden automatisch von der Teilnahme in diesem Kompatibilitätsmodus, und dieses Element ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e2877-138">Assemblies that have been compiled against earlier versions of the .NET Framework are automatically opted into this compatibility mode, and do not need this element.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="e2877-139">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="e2877-139">Configuration File</span></span>  
 <span data-ttu-id="e2877-140">Dieses Element kann nur in der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e2877-140">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2877-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e2877-141">Example</span></span>  
 <span data-ttu-id="e2877-142">Im folgenden Beispiel gezeigt ist wie für höhere resilienz gegen falsche optionale Plattformaufrufe Deklarationen für eine Anwendung, was zu langsameren Übergängen zwischen verwalteten und nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="e2877-142">The following example shows how to opt into increased resilience against incorrect platform invoke declarations for an application, at the cost of slower transitions between managed and unmanaged code.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_PInvokeStackResilience enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e2877-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2877-143">See also</span></span>
- [<span data-ttu-id="e2877-144">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="e2877-144">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="e2877-145">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="e2877-145">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="e2877-146">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="e2877-146">pInvokeStackImbalance</span></span>](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)
