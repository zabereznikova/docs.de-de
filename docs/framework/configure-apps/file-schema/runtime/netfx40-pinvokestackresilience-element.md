---
title: <NetFx40_PInvokeStackResilience>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f7a1cf34f63b1ba0dfced8ff23c252f3363723c6
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489412"
---
# <a name="netfx40pinvokestackresilience-element"></a><span data-ttu-id="bce28-102">\<NetFx40_PInvokeStackResilience >-Element</span><span class="sxs-lookup"><span data-stu-id="bce28-102">\<NetFx40_PInvokeStackResilience> Element</span></span>
<span data-ttu-id="bce28-103">Gibt an, ob die Runtime falsche Plattformaufrufdeklarationen zur Laufzeit automatisch korrigiert. Dies führt zu langsameren Übergängen zwischen verwaltetem und nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="bce28-103">Specifies whether the runtime automatically fixes incorrect platform invoke declarations at run time, at the cost of slower transitions between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="bce28-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bce28-104">\<configuration></span></span>  
<span data-ttu-id="bce28-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="bce28-105">\<runtime></span></span>  
<span data-ttu-id="bce28-106"><NetFx40_PInvokeStackResilience></span><span class="sxs-lookup"><span data-stu-id="bce28-106"><NetFx40_PInvokeStackResilience></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bce28-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="bce28-107">Syntax</span></span>  
  
```xml  
<NetFx40_PInvokeStackResilience  enabled="1|0"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bce28-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bce28-108">Attributes and Elements</span></span>  
 <span data-ttu-id="bce28-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bce28-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bce28-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="bce28-110">Attributes</span></span>  
  
|<span data-ttu-id="bce28-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="bce28-111">Attribute</span></span>|<span data-ttu-id="bce28-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bce28-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="bce28-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="bce28-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="bce28-114">Gibt an, ob die Runtime falsche Plattformaufrufdeklarationen erkennt Deklarationen und behebt automatisch auf 32-Bit-Plattformen zur Laufzeit den Stapel.</span><span class="sxs-lookup"><span data-stu-id="bce28-114">Specifies whether the runtime detects incorrect platform invoke declarations and automatically fixes the stack at run time on 32-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="bce28-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="bce28-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="bce28-116">Wert</span><span class="sxs-lookup"><span data-stu-id="bce28-116">Value</span></span>|<span data-ttu-id="bce28-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bce28-117">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="bce28-118">Die Common Language Runtime verwendet schneller Interop-Marshalling-Architektur eingeführt, die in .NET Framework 4, die nicht erkannt wurde, und beheben falsche Plattformaufrufdeklarationen.</span><span class="sxs-lookup"><span data-stu-id="bce28-118">The runtime uses the faster interop marshaling architecture introduced in the .NET Framework 4, which does not detect and fix incorrect platform invoke declarations.</span></span> <span data-ttu-id="bce28-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="bce28-119">This is the default.</span></span>|  
|`1`|<span data-ttu-id="bce28-120">Die Common Language Runtime verwendet langsameren Übergängen, die Erkennung und Behebung fehlerhafter Plattformaufrufdeklarationen.</span><span class="sxs-lookup"><span data-stu-id="bce28-120">The runtime uses slower transitions that detect and fix incorrect platform invoke declarations.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bce28-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bce28-121">Child Elements</span></span>  
 <span data-ttu-id="bce28-122">Keine</span><span class="sxs-lookup"><span data-stu-id="bce28-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bce28-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bce28-123">Parent Elements</span></span>  
  
|<span data-ttu-id="bce28-124">Element</span><span class="sxs-lookup"><span data-stu-id="bce28-124">Element</span></span>|<span data-ttu-id="bce28-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bce28-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bce28-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="bce28-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="bce28-127">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="bce28-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bce28-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bce28-128">Remarks</span></span>  
 <span data-ttu-id="bce28-129">Dieses Element können Sie eine Abstimmung zwischen schneller interop-Marshalling für Laufzeit resilienz gegen fehlerhafter Plattformaufruf Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="bce28-129">This element enables you to trade faster interop marshaling for run-time resilience against incorrect platform invoke declarations.</span></span>  
  
 <span data-ttu-id="bce28-130">Ab .NET Framework 4 bietet eine optimierte Architektur für das Interop-Marshalling eine deutliche leistungsverbesserung für Übergänge von verwaltetem Code an nicht verwalteten Code.</span><span class="sxs-lookup"><span data-stu-id="bce28-130">Starting with the .NET Framework 4, a streamlined interop marshaling architecture provides a significant performance improvement for transitions from managed code to unmanaged code.</span></span> <span data-ttu-id="bce28-131">In früheren Versionen von .NET Framework das Marshalling Ebene erkannt falsch Plattformaufrufmethode Deklarationen auf 32-Bit-Plattformen und automatisch korrigiert den Stapel.</span><span class="sxs-lookup"><span data-stu-id="bce28-131">In earlier versions of the .NET Framework, the marshaling layer detected incorrect platform invoke declarations on 32-bit platforms and automatically fixed the stack.</span></span> <span data-ttu-id="bce28-132">Die neue Architektur für Marshalling entfällt dieser Schritt.</span><span class="sxs-lookup"><span data-stu-id="bce28-132">The new marshaling architecture eliminates this step.</span></span> <span data-ttu-id="bce28-133">Daher sind Übergänge sehr schnell, aber es wird eine falsche Plattform aufrufen Deklaration einen Programmfehler verursachen können.</span><span class="sxs-lookup"><span data-stu-id="bce28-133">As a result, transitions are very fast, but an incorrect platform invoke declaration can cause a program failure.</span></span>  
  
 <span data-ttu-id="bce28-134">Um falsche Deklarationen zu erkennen, während der Entwicklung zu erleichtern, wurde der Visual Studio-Debuggingumgebung verbessert.</span><span class="sxs-lookup"><span data-stu-id="bce28-134">To make it easy to detect incorrect declarations during development, the Visual Studio debugging experience has been improved.</span></span> <span data-ttu-id="bce28-135">Die [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) -Assistent für verwaltetes Debuggens (MDA) informiert Sie über falschen Deklarationen aufrufen, wenn Ihre Anwendung mit dem angefügten Debugger ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bce28-135">The [pInvokeStackImbalance](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md) managed debugging assistant (MDA) notifies you of incorrect platform invoke declarations when your application is running with the debugger attached.</span></span>  
  
 <span data-ttu-id="bce28-136">Szenarien, in denen Ihre Anwendung Komponenten verwendet, die Sie nicht neu kompilieren, und haben falsche Plattformaufrufdeklarationen, können Sie verwenden, die `NetFx40_PInvokeStackResilience` Element.</span><span class="sxs-lookup"><span data-stu-id="bce28-136">To address scenarios where your application uses components that you cannot recompile, and that have incorrect platform invoke declarations, you can use the `NetFx40_PInvokeStackResilience` element.</span></span> <span data-ttu-id="bce28-137">Die Konfigurationsdatei der Anwendung mit diesem Element hinzugefügt `enabled="1"` "OPTS" in einem Kompatibilitätsmodus, mit dem Verhalten früherer Versionen von .NET Framework, was zu langsameren Übergängen.</span><span class="sxs-lookup"><span data-stu-id="bce28-137">Adding this element to your application configuration file with `enabled="1"` opts into a compatibility mode with the behavior of earlier versions of the .NET Framework, at the cost of slower transitions.</span></span> <span data-ttu-id="bce28-138">Assemblys, die auf früheren Versionen von .NET Framework kompiliert wurden, werden automatisch von der Teilnahme in diesem Kompatibilitätsmodus, und dieses Element ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bce28-138">Assemblies that have been compiled against earlier versions of the .NET Framework are automatically opted into this compatibility mode, and do not need this element.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="bce28-139">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="bce28-139">Configuration File</span></span>  
 <span data-ttu-id="bce28-140">Dieses Element kann nur in der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bce28-140">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bce28-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bce28-141">Example</span></span>  
 <span data-ttu-id="bce28-142">Im folgenden Beispiel gezeigt ist wie für höhere resilienz gegen falsche optionale Plattformaufrufe Deklarationen für eine Anwendung, was zu langsameren Übergängen zwischen verwalteten und nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="bce28-142">The following example shows how to opt into increased resilience against incorrect platform invoke declarations for an application, at the cost of slower transitions between managed and unmanaged code.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_PInvokeStackResilience enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bce28-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bce28-143">See also</span></span>

- [<span data-ttu-id="bce28-144">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="bce28-144">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="bce28-145">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="bce28-145">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="bce28-146">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="bce28-146">pInvokeStackImbalance</span></span>](../../../../../docs/framework/debug-trace-profile/pinvokestackimbalance-mda.md)
