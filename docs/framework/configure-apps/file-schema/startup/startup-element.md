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
ms.openlocfilehash: 634d9c5248c33619abec50d441d95c111febdcbf
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699415"
---
# <a name="startup-element"></a><span data-ttu-id="60872-102">\<startup >-Element</span><span class="sxs-lookup"><span data-stu-id="60872-102">\<startup> element</span></span>

<span data-ttu-id="60872-103">Gibt Common Language Runtime Startinformationen an.</span><span class="sxs-lookup"><span data-stu-id="60872-103">Specifies common language runtime startup information.</span></span>

[<span data-ttu-id="60872-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="60872-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="60872-105">&nbsp;&nbsp; **\<startup>**</span><span class="sxs-lookup"><span data-stu-id="60872-105">&nbsp;&nbsp;**\<startup>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="60872-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="60872-106">Syntax</span></span>

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" > 
</startup>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="60872-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="60872-107">Attributes and elements</span></span>

 <span data-ttu-id="60872-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="60872-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="60872-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="60872-109">Attributes</span></span>

|<span data-ttu-id="60872-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="60872-110">Attribute</span></span>|<span data-ttu-id="60872-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="60872-111">Description</span></span>|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|<span data-ttu-id="60872-112">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="60872-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="60872-113">Gibt an, ob die Richtlinie für die .NET Framework 2,0-Lauf Zeit Aktivierung aktiviert oder die .NET Framework 4-Aktivierungs Richtlinie verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="60872-113">Specifies whether to enable the .NET Framework 2.0 runtime activation policy or to use the .NET Framework 4 activation policy.</span></span>|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="60872-114">useLegacyV2RuntimeActivationPolicy-Attribut</span><span class="sxs-lookup"><span data-stu-id="60872-114">useLegacyV2RuntimeActivationPolicy attribute</span></span>

|<span data-ttu-id="60872-115">Wert</span><span class="sxs-lookup"><span data-stu-id="60872-115">Value</span></span>|<span data-ttu-id="60872-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="60872-116">Description</span></span>|
|-----------|-----------------|
|`true`|<span data-ttu-id="60872-117">Aktivieren Sie die Richtlinie für die .NET Framework 2,0-Lauf Zeit Aktivierung für die ausgewählte Laufzeit, die Legacy-Lauf Zeit Aktivierungs Techniken (z. b. die [CorBindToRuntimeEx-Funktion](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) an die von der Konfigurationsdatei gewählte Laufzeit bindet, anstatt Sie bei der CLR zu untersuchen. Version 2,0.</span><span class="sxs-lookup"><span data-stu-id="60872-117">Enable .NET Framework 2.0 runtime activation policy for the chosen runtime, which is to bind legacy runtime activation techniques (such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)) to the runtime chosen from the configuration file instead of capping them at CLR version 2.0.</span></span> <span data-ttu-id="60872-118">Wenn also CLR-Version 4 oder höher aus der Konfigurationsdatei ausgewählt wird, werden Assemblys im gemischten Modus, die mit früheren Versionen der .NET Framework erstellt wurden, mit der ausgewählten CLR-Version geladen.</span><span class="sxs-lookup"><span data-stu-id="60872-118">Thus, if CLR version 4 or later is chosen from the configuration file, mixed-mode assemblies created with earlier versions of the .NET Framework are loaded with the chosen CLR version.</span></span> <span data-ttu-id="60872-119">Durch Festlegen dieses Werts wird verhindert, dass CLR-Version 1,1 oder CLR-Version 2,0 in denselben Prozess geladen wird, wodurch die Prozess interne parallele Funktion deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="60872-119">Setting this value prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature.</span></span>|
|`false`|<span data-ttu-id="60872-120">Verwenden Sie die Standard Aktivierungs Richtlinie für die .NET Framework 4 und höher, damit ältere Lauf Zeit Aktivierungs Techniken die CLR-Version 1,1 oder 2,0 in den Prozess laden können.</span><span class="sxs-lookup"><span data-stu-id="60872-120">Use the default activation policy for the .NET Framework 4 and later, which is to allow legacy runtime activation techniques to load CLR version 1.1 or 2.0 into the process.</span></span> <span data-ttu-id="60872-121">Durch Festlegen dieses Werts wird verhindert, dass Assemblys im gemischten Modus in die .NET Framework 4 oder höher geladen werden, es sei denn, Sie wurden mit dem .NET Framework 4 oder höher erstellt</span><span class="sxs-lookup"><span data-stu-id="60872-121">Setting this value prevents mixed-mode assemblies from loading into the .NET Framework 4 or later unless they were built with the .NET Framework 4 or later.</span></span> <span data-ttu-id="60872-122">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="60872-122">This value is the default.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="60872-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="60872-123">Child elements</span></span>

|<span data-ttu-id="60872-124">Element</span><span class="sxs-lookup"><span data-stu-id="60872-124">Element</span></span>|<span data-ttu-id="60872-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="60872-125">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="60872-126">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="60872-126">\<requiredRuntime></span></span>](requiredruntime-element.md)|<span data-ttu-id="60872-127">Gibt an, dass die Anwendung nur Version 1.0 der Common Language Runtime unterstützt.</span><span class="sxs-lookup"><span data-stu-id="60872-127">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="60872-128">Anwendungen, die mit der Runtime-Version 1,1 oder höher erstellt wurden, sollten das **\<supportedruntime->-** Element verwenden.</span><span class="sxs-lookup"><span data-stu-id="60872-128">Applications built with runtime version 1.1 or later should use the **\<supportedRuntime>** element.</span></span>|
|[<span data-ttu-id="60872-129">\<supportedRuntime></span><span class="sxs-lookup"><span data-stu-id="60872-129">\<supportedRuntime></span></span>](supportedruntime-element.md)|<span data-ttu-id="60872-130">Gibt an, welche Versionen der Common Language Runtime von der Anwendung unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="60872-130">Specifies which versions of the common language runtime the application supports.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="60872-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="60872-131">Parent elements</span></span>

|<span data-ttu-id="60872-132">Element</span><span class="sxs-lookup"><span data-stu-id="60872-132">Element</span></span>|<span data-ttu-id="60872-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="60872-133">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="60872-134">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="60872-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|

## <a name="remarks"></a><span data-ttu-id="60872-135">Hinweise</span><span class="sxs-lookup"><span data-stu-id="60872-135">Remarks</span></span>

 <span data-ttu-id="60872-136">Das **\<supportedruntime->** Element sollte von allen Anwendungen verwendet werden, die mit Version 1,1 oder höher der Laufzeit erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="60872-136">The **\<supportedRuntime>** element should be used by all applications built using version 1.1 or later of the runtime.</span></span> <span data-ttu-id="60872-137">Anwendungen, die zur Unterstützung von nur Version 1,0 der Laufzeit erstellt wurden, müssen das **\<requirements druntime >-** Element verwenden.</span><span class="sxs-lookup"><span data-stu-id="60872-137">Applications built to support only version 1.0 of the runtime must use the **\<requiredRuntime>** element.</span></span>

 <span data-ttu-id="60872-138">Der Startcode für eine in Microsoft Internet Explorer gehostete Anwendung ignoriert das **\<startup >-** Element und seine untergeordneten Elemente.</span><span class="sxs-lookup"><span data-stu-id="60872-138">The startup code for an application hosted in Microsoft Internet Explorer ignores the **\<startup>** element and its child elements.</span></span>

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a><span data-ttu-id="60872-139">Das useLegacyV2RuntimeActivationPolicy-Attribut</span><span class="sxs-lookup"><span data-stu-id="60872-139">The useLegacyV2RuntimeActivationPolicy attribute</span></span>

 <span data-ttu-id="60872-140">Dieses Attribut ist nützlich, wenn Ihre Anwendung ältere Aktivierungs Pfade verwendet, wie z. b. die [CorBindToRuntimeEx-Funktion](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), und Sie möchten, dass diese Pfade Version 4 der CLR anstelle einer früheren Version aktivieren, oder wenn Ihre Anwendung mit .NET erstellt wurde. Framework 4, aber eine Abhängigkeit von einer Assembly im gemischten Modus, die mit einer früheren Version des .NET Framework erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="60872-140">This attribute is useful if your application uses legacy activation paths, such as the [CorBindToRuntimeEx function](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md), and you want those paths to activate version 4 of the CLR instead of an earlier version, or if your application is built with the .NET Framework 4 but has a dependency on a mixed-mode assembly built with an earlier version of the .NET Framework.</span></span> <span data-ttu-id="60872-141">Legen Sie in diesen Szenarien das-Attribut auf `true` fest.</span><span class="sxs-lookup"><span data-stu-id="60872-141">In those scenarios, set the attribute to `true`.</span></span>

> [!NOTE]
> <span data-ttu-id="60872-142">Wenn das-Attribut auf `true` festgelegt wird, wird verhindert, dass CLR-Version 1,1 oder CLR-Version 2,0 in denselben Prozess geladen wird, wodurch die Prozess interne parallele Funktion deaktiviert wird (siehe parallele [Ausführung für COM-Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span><span class="sxs-lookup"><span data-stu-id="60872-142">Setting the attribute to `true` prevents CLR version 1.1 or CLR version 2.0 from loading into the same process, effectively disabling the in-process side-by-side feature (see [Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))).</span></span>

## <a name="example"></a><span data-ttu-id="60872-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="60872-143">Example</span></span>

 <span data-ttu-id="60872-144">Im folgenden Beispiel wird gezeigt, wie die Laufzeitversion in einer Konfigurationsdatei angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="60872-144">The following example shows how to specify the runtime version in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="60872-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60872-145">See also</span></span>

- [<span data-ttu-id="60872-146">Startup Settings Schema (Schema für Starteinstellungen)</span><span class="sxs-lookup"><span data-stu-id="60872-146">Startup Settings Schema</span></span>](index.md)
- [<span data-ttu-id="60872-147">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="60872-147">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="60872-148">Vorgehensweise: Konfigurieren einer App zur Unterstützung von .NET Framework 4 oder höher</span><span class="sxs-lookup"><span data-stu-id="60872-148">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- <span data-ttu-id="60872-149">[Parallele Ausführung für COM-Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="60872-149">[Side-by-Side Execution for COM Interop](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))</span></span>
- [<span data-ttu-id="60872-150">Prozessinterne parallele Ausführung</span><span class="sxs-lookup"><span data-stu-id="60872-150">In-Process Side-by-Side Execution</span></span>](../../../deployment/in-process-side-by-side-execution.md)
