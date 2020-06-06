---
title: <NetFx40_PInvokeStackResilience>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
ms.openlocfilehash: 86f50aafe0b21d5080288e09ac7118ca1e4c939a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73116161"
---
# <a name="netfx40_pinvokestackresilience-element"></a><span data-ttu-id="6d97e-102">\<NetFx40_PInvokeStackResilience>-Element</span><span class="sxs-lookup"><span data-stu-id="6d97e-102">\<NetFx40_PInvokeStackResilience> Element</span></span>

<span data-ttu-id="6d97e-103">Gibt an, ob die Runtime falsche Plattformaufrufdeklarationen zur Laufzeit automatisch korrigiert. Dies führt zu langsameren Übergängen zwischen verwaltetem und nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="6d97e-103">Specifies whether the runtime automatically fixes incorrect platform invoke declarations at run time, at the cost of slower transitions between managed and unmanaged code.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx40_PInvokeStackResilience>**  

## <a name="syntax"></a><span data-ttu-id="6d97e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6d97e-104">Syntax</span></span>

```xml
<NetFx40_PInvokeStackResilience  enabled="1|0"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6d97e-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6d97e-105">Attributes and Elements</span></span>

<span data-ttu-id="6d97e-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6d97e-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="6d97e-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="6d97e-107">Attributes</span></span>

|<span data-ttu-id="6d97e-108">attribute</span><span class="sxs-lookup"><span data-stu-id="6d97e-108">Attribute</span></span>|<span data-ttu-id="6d97e-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6d97e-109">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="6d97e-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="6d97e-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="6d97e-111">Gibt an, ob die Laufzeit falsche Platt Form Aufruf Deklarationen erkennt und den Stapel zur Laufzeit auf 32-Bit-Plattformen automatisch korrigiert.</span><span class="sxs-lookup"><span data-stu-id="6d97e-111">Specifies whether the runtime detects incorrect platform invoke declarations and automatically fixes the stack at run time on 32-bit platforms.</span></span>|

## <a name="enabled-attribute"></a><span data-ttu-id="6d97e-112">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="6d97e-112">enabled Attribute</span></span>

|<span data-ttu-id="6d97e-113">Wert</span><span class="sxs-lookup"><span data-stu-id="6d97e-113">Value</span></span>|<span data-ttu-id="6d97e-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6d97e-114">Description</span></span>|
|-----------|-----------------|
|`0`|<span data-ttu-id="6d97e-115">Die Laufzeit verwendet die schnellere Interop-marshallingarchitektur, die in der .NET Framework 4 eingeführt wurde, die falsche Platt Form Aufruf Deklarationen nicht erkennt und repariert.</span><span class="sxs-lookup"><span data-stu-id="6d97e-115">The runtime uses the faster interop marshaling architecture introduced in the .NET Framework 4, which does not detect and fix incorrect platform invoke declarations.</span></span> <span data-ttu-id="6d97e-116">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="6d97e-116">This is the default.</span></span>|
|`1`|<span data-ttu-id="6d97e-117">Die Laufzeit verwendet langsamere Übergänge, die falsche Platt Form Aufruf Deklarationen erkennen und beheben.</span><span class="sxs-lookup"><span data-stu-id="6d97e-117">The runtime uses slower transitions that detect and fix incorrect platform invoke declarations.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="6d97e-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6d97e-118">Child Elements</span></span>

<span data-ttu-id="6d97e-119">Keine</span><span class="sxs-lookup"><span data-stu-id="6d97e-119">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6d97e-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6d97e-120">Parent Elements</span></span>

|<span data-ttu-id="6d97e-121">Element</span><span class="sxs-lookup"><span data-stu-id="6d97e-121">Element</span></span>|<span data-ttu-id="6d97e-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6d97e-122">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="6d97e-123">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="6d97e-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="6d97e-124">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="6d97e-124">Contains information about runtime initialization options.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6d97e-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6d97e-125">Remarks</span></span>

<span data-ttu-id="6d97e-126">Mit diesem Element können Sie ein schnelleres Interop-Marshalling für die Lauf Zeit Resilienz gegen falsche Platt Form Aufruf Deklarationen durchführen.</span><span class="sxs-lookup"><span data-stu-id="6d97e-126">This element enables you to trade faster interop marshaling for run-time resilience against incorrect platform invoke declarations.</span></span>

<span data-ttu-id="6d97e-127">Ab .NET Framework 4 bietet eine optimierte Interop-marshallingarchitektur eine bedeutende Leistungsverbesserung bei Übergängen von verwaltetem Code zu nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="6d97e-127">Starting with the .NET Framework 4, a streamlined interop marshaling architecture provides a significant performance improvement for transitions from managed code to unmanaged code.</span></span> <span data-ttu-id="6d97e-128">In früheren Versionen der .NET Framework erkannte die Marshallingschicht falsche Platt Form Aufruf Deklarationen auf 32-Bit-Plattformen und hat den Stapel automatisch korrigiert.</span><span class="sxs-lookup"><span data-stu-id="6d97e-128">In earlier versions of the .NET Framework, the marshaling layer detected incorrect platform invoke declarations on 32-bit platforms and automatically fixed the stack.</span></span> <span data-ttu-id="6d97e-129">In der neuen marshallingarchitektur ist dieser Schritt ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="6d97e-129">The new marshaling architecture eliminates this step.</span></span> <span data-ttu-id="6d97e-130">Folglich sind Übergänge sehr schnell, aber eine falsche Platt Form Aufruf Deklaration kann einen Programmfehler verursachen.</span><span class="sxs-lookup"><span data-stu-id="6d97e-130">As a result, transitions are very fast, but an incorrect platform invoke declaration can cause a program failure.</span></span>

<span data-ttu-id="6d97e-131">Um das erkennen falscher Deklarationen während der Entwicklung zu vereinfachen, wurde die Visual Studio-debuggingdarstellung verbessert.</span><span class="sxs-lookup"><span data-stu-id="6d97e-131">To make it easy to detect incorrect declarations during development, the Visual Studio debugging experience has been improved.</span></span> <span data-ttu-id="6d97e-132">Der [pinvokestackungleichsverwaltungs](../../../debug-trace-profile/pinvokestackimbalance-mda.md) -Assistent für verwaltetes Debuggen (MDA) benachrichtigt Sie über falsche Platt Form Aufruf Deklarationen, wenn die Anwendung mit dem angefügten Debugger ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6d97e-132">The [pInvokeStackImbalance](../../../debug-trace-profile/pinvokestackimbalance-mda.md) managed debugging assistant (MDA) notifies you of incorrect platform invoke declarations when your application is running with the debugger attached.</span></span>

<span data-ttu-id="6d97e-133">Sie können das-Element verwenden, um Szenarios zu behandeln, in denen Ihre Anwendung Komponenten verwendet, die Sie nicht neu kompilieren können und falsche Platt Form Aufruf Deklarationen aufweisen `NetFx40_PInvokeStackResilience` .</span><span class="sxs-lookup"><span data-stu-id="6d97e-133">To address scenarios where your application uses components that you cannot recompile, and that have incorrect platform invoke declarations, you can use the `NetFx40_PInvokeStackResilience` element.</span></span> <span data-ttu-id="6d97e-134">Wenn Sie dieses Element der Anwendungs Konfigurationsdatei mit `enabled="1"` opts in einen Kompatibilitätsmodus mit dem Verhalten früherer Versionen der .NET Framework hinzufügen, wird dies zu langsameren Übergängen.</span><span class="sxs-lookup"><span data-stu-id="6d97e-134">Adding this element to your application configuration file with `enabled="1"` opts into a compatibility mode with the behavior of earlier versions of the .NET Framework, at the cost of slower transitions.</span></span> <span data-ttu-id="6d97e-135">Assemblys, die mit früheren Versionen der .NET Framework kompiliert wurden, werden automatisch in diesen Kompatibilitätsmodus gewählt und benötigen dieses Element nicht.</span><span class="sxs-lookup"><span data-stu-id="6d97e-135">Assemblies that have been compiled against earlier versions of the .NET Framework are automatically opted into this compatibility mode, and do not need this element.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="6d97e-136">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="6d97e-136">Configuration File</span></span>

<span data-ttu-id="6d97e-137">Dieses Element kann nur in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6d97e-137">This element can be used only in the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="6d97e-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6d97e-138">Example</span></span>

<span data-ttu-id="6d97e-139">Im folgenden Beispiel wird gezeigt, wie die Resilienz gegenüber falschen Platt Form Aufruf Deklarationen für eine Anwendung verbessert werden kann, was zu langsameren Übergängen zwischen verwaltetem und nicht verwaltetem Code geführt hat.</span><span class="sxs-lookup"><span data-stu-id="6d97e-139">The following example shows how to opt into increased resilience against incorrect platform invoke declarations for an application, at the cost of slower transitions between managed and unmanaged code.</span></span>

```xml
<configuration>
   <runtime>
      <NetFx40_PInvokeStackResilience enabled="1"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="6d97e-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6d97e-140">See also</span></span>

- [<span data-ttu-id="6d97e-141">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="6d97e-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6d97e-142">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="6d97e-142">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="6d97e-143">pInvokeStackImbalance</span><span class="sxs-lookup"><span data-stu-id="6d97e-143">pInvokeStackImbalance</span></span>](../../../debug-trace-profile/pinvokestackimbalance-mda.md)
