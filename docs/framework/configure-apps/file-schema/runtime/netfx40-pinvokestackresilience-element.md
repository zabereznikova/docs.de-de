---
title: <NetFx40_PInvokeStackResilience>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
ms.openlocfilehash: 86f50aafe0b21d5080288e09ac7118ca1e4c939a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116161"
---
# <a name="netfx40_pinvokestackresilience-element"></a><span data-ttu-id="af5ee-102">\<NetFx40_PInvokeStackResilience >-Element</span><span class="sxs-lookup"><span data-stu-id="af5ee-102">\<NetFx40_PInvokeStackResilience> Element</span></span>

<span data-ttu-id="af5ee-103">Gibt an, ob die Runtime falsche Plattformaufrufdeklarationen zur Laufzeit automatisch korrigiert. Dies führt zu langsameren Übergängen zwischen verwaltetem und nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="af5ee-103">Specifies whether the runtime automatically fixes incorrect platform invoke declarations at run time, at the cost of slower transitions between managed and unmanaged code.</span></span>

<span data-ttu-id="af5ee-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="af5ee-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="af5ee-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="af5ee-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="af5ee-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<NetFx40_PInvokeStackResilience >**</span><span class="sxs-lookup"><span data-stu-id="af5ee-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx40_PInvokeStackResilience>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="af5ee-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="af5ee-107">Syntax</span></span>

```xml
<NetFx40_PInvokeStackResilience  enabled="1|0"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="af5ee-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="af5ee-108">Attributes and Elements</span></span>

<span data-ttu-id="af5ee-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="af5ee-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="af5ee-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="af5ee-110">Attributes</span></span>

|<span data-ttu-id="af5ee-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="af5ee-111">Attribute</span></span>|<span data-ttu-id="af5ee-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af5ee-112">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="af5ee-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="af5ee-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="af5ee-114">Gibt an, ob die Laufzeit falsche Platt Form Aufruf Deklarationen erkennt und den Stapel zur Laufzeit auf 32-Bit-Plattformen automatisch korrigiert.</span><span class="sxs-lookup"><span data-stu-id="af5ee-114">Specifies whether the runtime detects incorrect platform invoke declarations and automatically fixes the stack at run time on 32-bit platforms.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="af5ee-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="af5ee-115">enabled Attribute</span></span>

|<span data-ttu-id="af5ee-116">Wert</span><span class="sxs-lookup"><span data-stu-id="af5ee-116">Value</span></span>|<span data-ttu-id="af5ee-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af5ee-117">Description</span></span>|
|-----------|-----------------|
|`0`|<span data-ttu-id="af5ee-118">Die Laufzeit verwendet die schnellere Interop-marshallingarchitektur, die in der .NET Framework 4 eingeführt wurde, die falsche Platt Form Aufruf Deklarationen nicht erkennt und repariert.</span><span class="sxs-lookup"><span data-stu-id="af5ee-118">The runtime uses the faster interop marshaling architecture introduced in the .NET Framework 4, which does not detect and fix incorrect platform invoke declarations.</span></span> <span data-ttu-id="af5ee-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="af5ee-119">This is the default.</span></span>|
|`1`|<span data-ttu-id="af5ee-120">Die Laufzeit verwendet langsamere Übergänge, die falsche Platt Form Aufruf Deklarationen erkennen und beheben.</span><span class="sxs-lookup"><span data-stu-id="af5ee-120">The runtime uses slower transitions that detect and fix incorrect platform invoke declarations.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="af5ee-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="af5ee-121">Child Elements</span></span>

<span data-ttu-id="af5ee-122">Keine</span><span class="sxs-lookup"><span data-stu-id="af5ee-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="af5ee-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="af5ee-123">Parent Elements</span></span>

|<span data-ttu-id="af5ee-124">Element</span><span class="sxs-lookup"><span data-stu-id="af5ee-124">Element</span></span>|<span data-ttu-id="af5ee-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af5ee-125">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="af5ee-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="af5ee-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="af5ee-127">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="af5ee-127">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="af5ee-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="af5ee-128">Remarks</span></span>

<span data-ttu-id="af5ee-129">Mit diesem Element können Sie ein schnelleres Interop-Marshalling für die Lauf Zeit Resilienz gegen falsche Platt Form Aufruf Deklarationen durchführen.</span><span class="sxs-lookup"><span data-stu-id="af5ee-129">This element enables you to trade faster interop marshaling for run-time resilience against incorrect platform invoke declarations.</span></span>

<span data-ttu-id="af5ee-130">Ab .NET Framework 4 bietet eine optimierte Interop-marshallingarchitektur eine bedeutende Leistungsverbesserung bei Übergängen von verwaltetem Code zu nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="af5ee-130">Starting with the .NET Framework 4, a streamlined interop marshaling architecture provides a significant performance improvement for transitions from managed code to unmanaged code.</span></span> <span data-ttu-id="af5ee-131">In früheren Versionen der .NET Framework erkannte die Marshallingschicht falsche Platt Form Aufruf Deklarationen auf 32-Bit-Plattformen und hat den Stapel automatisch korrigiert.</span><span class="sxs-lookup"><span data-stu-id="af5ee-131">In earlier versions of the .NET Framework, the marshaling layer detected incorrect platform invoke declarations on 32-bit platforms and automatically fixed the stack.</span></span> <span data-ttu-id="af5ee-132">In der neuen marshallingarchitektur ist dieser Schritt ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="af5ee-132">The new marshaling architecture eliminates this step.</span></span> <span data-ttu-id="af5ee-133">Folglich sind Übergänge sehr schnell, aber eine falsche Platt Form Aufruf Deklaration kann einen Programmfehler verursachen.</span><span class="sxs-lookup"><span data-stu-id="af5ee-133">As a result, transitions are very fast, but an incorrect platform invoke declaration can cause a program failure.</span></span>

<span data-ttu-id="af5ee-134">Um das erkennen falscher Deklarationen während der Entwicklung zu vereinfachen, wurde die Visual Studio-debuggingdarstellung verbessert.</span><span class="sxs-lookup"><span data-stu-id="af5ee-134">To make it easy to detect incorrect declarations during development, the Visual Studio debugging experience has been improved.</span></span> <span data-ttu-id="af5ee-135">Der [pinvokestackungleichsverwaltungs](../../../debug-trace-profile/pinvokestackimbalance-mda.md) -Assistent für verwaltetes Debuggen (MDA) benachrichtigt Sie über falsche Platt Form Aufruf Deklarationen, wenn die Anwendung mit dem angefügten Debugger ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="af5ee-135">The [pInvokeStackImbalance](../../../debug-trace-profile/pinvokestackimbalance-mda.md) managed debugging assistant (MDA) notifies you of incorrect platform invoke declarations when your application is running with the debugger attached.</span></span>

<span data-ttu-id="af5ee-136">Zum Behandeln von Szenarien, in denen Ihre Anwendung Komponenten verwendet, die Sie nicht neu kompilieren können und falsche Platt Form Aufruf Deklarationen aufweisen, können Sie das `NetFx40_PInvokeStackResilience`-Element verwenden.</span><span class="sxs-lookup"><span data-stu-id="af5ee-136">To address scenarios where your application uses components that you cannot recompile, and that have incorrect platform invoke declarations, you can use the `NetFx40_PInvokeStackResilience` element.</span></span> <span data-ttu-id="af5ee-137">Wenn Sie dieses Element der Anwendungs Konfigurationsdatei hinzufügen und `enabled="1"` opts in einen Kompatibilitätsmodus mit dem Verhalten früherer Versionen des .NET Framework mit den Kosten langsamer Übergänge.</span><span class="sxs-lookup"><span data-stu-id="af5ee-137">Adding this element to your application configuration file with `enabled="1"` opts into a compatibility mode with the behavior of earlier versions of the .NET Framework, at the cost of slower transitions.</span></span> <span data-ttu-id="af5ee-138">Assemblys, die mit früheren Versionen der .NET Framework kompiliert wurden, werden automatisch in diesen Kompatibilitätsmodus gewählt und benötigen dieses Element nicht.</span><span class="sxs-lookup"><span data-stu-id="af5ee-138">Assemblies that have been compiled against earlier versions of the .NET Framework are automatically opted into this compatibility mode, and do not need this element.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="af5ee-139">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="af5ee-139">Configuration File</span></span>

<span data-ttu-id="af5ee-140">Dieses Element kann nur in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="af5ee-140">This element can be used only in the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="af5ee-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="af5ee-141">Example</span></span>

<span data-ttu-id="af5ee-142">Im folgenden Beispiel wird gezeigt, wie die Resilienz gegenüber falschen Platt Form Aufruf Deklarationen für eine Anwendung verbessert werden kann, was zu langsameren Übergängen zwischen verwaltetem und nicht verwaltetem Code geführt hat.</span><span class="sxs-lookup"><span data-stu-id="af5ee-142">The following example shows how to opt into increased resilience against incorrect platform invoke declarations for an application, at the cost of slower transitions between managed and unmanaged code.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_PInvokeStackResilience enabled="1"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="af5ee-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af5ee-143">See also</span></span>

- [<span data-ttu-id="af5ee-144">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="af5ee-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="af5ee-145">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="af5ee-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="af5ee-146">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="af5ee-146">pInvokeStackImbalance</span></span>](../../../debug-trace-profile/pinvokestackimbalance-mda.md)
