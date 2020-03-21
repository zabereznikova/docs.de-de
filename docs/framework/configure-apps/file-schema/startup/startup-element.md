---
title: <startup>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
ms.openlocfilehash: e936c069275bfa9f7ac81ef1c6fc6228828182a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153729"
---
# <a name="startup-element"></a><span data-ttu-id="90d80-102">\<Start>-Element</span><span class="sxs-lookup"><span data-stu-id="90d80-102">\<startup> element</span></span>

<span data-ttu-id="90d80-103">Gibt allgemeine Laufzeitstartinformationen an.</span><span class="sxs-lookup"><span data-stu-id="90d80-103">Specifies common language runtime startup information.</span></span>

[<span data-ttu-id="90d80-104">**\<Konfiguration>**</span><span class="sxs-lookup"><span data-stu-id="90d80-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="90d80-105">&nbsp;&nbsp;**\<Startup->**</span><span class="sxs-lookup"><span data-stu-id="90d80-105">&nbsp;&nbsp;**\<startup>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="90d80-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="90d80-106">Syntax</span></span>

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" >
</startup>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="90d80-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="90d80-107">Attributes and elements</span></span>

 <span data-ttu-id="90d80-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="90d80-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="90d80-109">Attributes</span><span class="sxs-lookup"><span data-stu-id="90d80-109">Attributes</span></span>

|<span data-ttu-id="90d80-110">attribute</span><span class="sxs-lookup"><span data-stu-id="90d80-110">Attribute</span></span>|<span data-ttu-id="90d80-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90d80-111">Description</span></span>|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="90d80-112">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="90d80-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="90d80-113">Gibt an, ob die .NET Framework 2.0-Laufzeitaktivierungsrichtlinie aktiviert oder die .NET Framework 4-Aktivierungsrichtlinie verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="90d80-113">Specifies whether to enable the .NET Framework 2.0 runtime activation policy or to use the .NET Framework 4 activation policy.</span></span>|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="90d80-114">useLegacyV2RuntimeActivationPolicy-Attribut</span><span class="sxs-lookup"><span data-stu-id="90d80-114">useLegacyV2RuntimeActivationPolicy attribute</span></span>

|<span data-ttu-id="90d80-115">value</span><span class="sxs-lookup"><span data-stu-id="90d80-115">Value</span></span>|<span data-ttu-id="90d80-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90d80-116">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="90d80-117">Aktivieren Sie .NET Framework 2.0-Laufzeitaktivierungsrichtlinie für die gewählte Laufzeit, d. h. ältere Laufzeitaktivierungstechniken (z. B. [die CorBindToRuntimeEx-Funktion)](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)an die laufzeitweise zu binden, die aus der Konfigurationsdatei ausgewählt wurde, anstatt sie mit CLR-Version 2.0 zu deckeln.</span><span class="sxs-lookup"><span data-stu-id="90d80-117">Enable .NET Framework 2.0 runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="90d80-118">Wenn also CLR-Version 4 oder höher aus der Konfigurationsdatei ausgewählt wird, werden Assemblys im gemischten Modus, die mit früheren Versionen von .NET Framework erstellt wurden, mit der ausgewählten CLR-Version geladen.</span><span class="sxs-lookup"><span data-stu-id="90d80-118">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="90d80-119">Durch Festlegen dieses Werts wird verhindert, dass CLR-Version 1.1 oder CLR-Version 2.0 in denselben Prozess geladen wird, wodurch das Prozess-Side-by-Side-Feature effektiv deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="90d80-119">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|
|`false`|<span data-ttu-id="90d80-120">Verwenden Sie die Standardaktivierungsrichtlinie für .NET Framework 4 und höher, d. h. die Verwendung von Legacy-Laufzeitaktivierungstechniken zum Laden von CLR-Version 1.1 oder 2.0 in den Prozess.</span><span class="sxs-lookup"><span data-stu-id="90d80-120">Use the default activation policy for the .NET Framework 4 and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="90d80-121">Durch Festlegen dieses Werts wird verhindert, dass Assemblys mit gemischtem Modus in .NET Framework 4 oder höher geladen werden, es sei denn, sie wurden mit .NET Framework 4 oder höher erstellt.</span><span class="sxs-lookup"><span data-stu-id="90d80-121">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="90d80-122">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="90d80-122">This value is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="90d80-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="90d80-123">Child elements</span></span>

|<span data-ttu-id="90d80-124">Element</span><span class="sxs-lookup"><span data-stu-id="90d80-124">Element</span></span>|<span data-ttu-id="90d80-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90d80-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="90d80-126">\<erforderlichDauer></span><span class="sxs-lookup"><span data-stu-id="90d80-126">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="90d80-127">Gibt an, dass die Anwendung nur Version 1.0 der Common Language Runtime unterstützt.</span><span class="sxs-lookup"><span data-stu-id="90d80-127">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="90d80-128">Anwendungen, die mit Derlaufzeitversion 1.1 oder höher erstellt wurden, sollten das \*\* \<unterstützteRuntime>-Element\*\* verwenden.</span><span class="sxs-lookup"><span data-stu-id="90d80-128">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|
|[<span data-ttu-id="90d80-129">\<unterstützteRuntime-></span><span class="sxs-lookup"><span data-stu-id="90d80-129">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="90d80-130">Gibt an, welche Versionen der Common Language Runtime von der Anwendung unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="90d80-130">Specifies which versions of the common language runtime the application supports.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="90d80-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="90d80-131">Parent elements</span></span>

|<span data-ttu-id="90d80-132">Element</span><span class="sxs-lookup"><span data-stu-id="90d80-132">Element</span></span>|<span data-ttu-id="90d80-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90d80-133">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="90d80-134">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="90d80-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="90d80-135">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="90d80-135">Remarks</span></span>

 <span data-ttu-id="90d80-136">Das \*\* \<unterstützteRuntime->-Element\*\* sollte von allen Anwendungen verwendet werden, die mit Version 1.1 oder höher der Laufzeit erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="90d80-136">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="90d80-137">Anwendungen, die nur Version 1.0 der Laufzeit unterstützen, müssen das \*\* \<erforderlicheRuntime->-Element\*\* verwenden.</span><span class="sxs-lookup"><span data-stu-id="90d80-137">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>

 <span data-ttu-id="90d80-138">Der Startcode für eine in Microsoft Internet \*\* \<\*\* Explorer gehostete Anwendung ignoriert den Start>-Elements und seine untergeordneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="90d80-138">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="90d80-139">Das useLegacyV2RuntimeActivationPolicy-Attribut</span><span class="sxs-lookup"><span data-stu-id="90d80-139">The useLegacyV2RuntimeActivationPolicy attribute</span></span>

 <span data-ttu-id="90d80-140">Dieses Attribut ist nützlich, wenn Ihre Anwendung ältere Aktivierungspfade verwendet, z. B. die [CorBindToRuntimeTimeEx-Funktion](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), und Sie möchten, dass diese Pfade Version 4 der CLR anstelle einer früheren Version aktivieren, oder wenn Ihre Anwendung mit .NET Framework 4 erstellt wird, aber von einer Assembly im gemischten Modus abhängig ist, die mit einer früheren Version von .NET Framework erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="90d80-140">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the .NET Framework 4 but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="90d80-141">Legen Sie in diesen `true`Szenarien das Attribut auf .</span><span class="sxs-lookup"><span data-stu-id="90d80-141">In those scenarios, set the attribute to `true`.</span></span>

> [!NOTE]
> <span data-ttu-id="90d80-142">Festlegen des `true` Attributs, um zu verhindern, dass CLR-Version 1.1 oder CLR-Version 2.0 in denselben Prozess geladen wird, wodurch das prozessübergreifende Side-by-Side-Feature effektiv deaktiviert wird (siehe [Side-by-Side-Ausführung für COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span><span class="sxs-lookup"><span data-stu-id="90d80-142">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span></span>

## <a name="example"></a><span data-ttu-id="90d80-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90d80-143">Example</span></span>

 <span data-ttu-id="90d80-144">Das folgende Beispiel zeigt, wie Sie die Laufzeitversion in einer Konfigurationsdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="90d80-144">The following example shows how to specify the runtime version in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="90d80-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90d80-145">See also</span></span>

- [<span data-ttu-id="90d80-146">Starteinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="90d80-146">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="90d80-147">Schema der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="90d80-147">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="90d80-148">Gewusst wie: Konfigurieren einer App zur Unterstützung von .NET Framework 4 oder neueren Versionen</span><span class="sxs-lookup"><span data-stu-id="90d80-148">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- <span data-ttu-id="90d80-149">[Parallele Ausführung für COM-Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="90d80-149">[Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span></span>
- [<span data-ttu-id="90d80-150">Prozessinterne parallele Ausführung</span><span class="sxs-lookup"><span data-stu-id="90d80-150">In-Process Side-by-Side Execution</span></span>](../../../deployment/in-process-side-by-side-execution.md)
