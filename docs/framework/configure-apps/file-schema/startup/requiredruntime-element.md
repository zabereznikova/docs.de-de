---
title: '&lt;RequiredRuntime&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 633769573253d7516bc50f0210c30376e6aa230a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltrequiredruntimegt-element"></a><span data-ttu-id="e4235-102">&lt;RequiredRuntime&gt; Element</span><span class="sxs-lookup"><span data-stu-id="e4235-102">&lt;requiredRuntime&gt; Element</span></span>
<span data-ttu-id="e4235-103">Gibt an, dass die Anwendung nur Version 1.0 der Common Language Runtime unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e4235-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="e4235-104">Dieses Element ist veraltet und sollte nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e4235-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="e4235-105">Die [ `supportedRuntime` ](supportedruntime-element.md) -Element sollte stattdessen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e4235-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>
  
 <span data-ttu-id="e4235-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e4235-106">\<configuration></span></span>  
<span data-ttu-id="e4235-107">\<Start ></span><span class="sxs-lookup"><span data-stu-id="e4235-107">\<startup></span></span>  
<span data-ttu-id="e4235-108">\<RequiredRuntime ></span><span class="sxs-lookup"><span data-stu-id="e4235-108">\<requiredRuntime></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4235-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4235-109">Syntax</span></span>  
  
```xml  
   <requiredRuntime    
version="runtime version"  
safemode="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e4235-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e4235-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e4235-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e4235-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e4235-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="e4235-112">Attributes</span></span>  
  
|<span data-ttu-id="e4235-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="e4235-113">Attribute</span></span>|<span data-ttu-id="e4235-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e4235-114">Description</span></span>|  
|---------------|-----------------|  
|`version`|<span data-ttu-id="e4235-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="e4235-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="e4235-116">Ein Zeichenfolgenwert, der die Version von .NET Framework angibt, die diese Anwendung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e4235-116">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="e4235-117">Der String-Wert muss es sich um den Namen des Verzeichnisses finden Sie unter .NET Framework-Installationsstammverzeichnis übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="e4235-117">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="e4235-118">Der Inhalt des Zeichenfolgenwerts wird nicht analysiert.</span><span class="sxs-lookup"><span data-stu-id="e4235-118">The contents of the string value are not parsed.</span></span>|  
|`safemode`|<span data-ttu-id="e4235-119">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="e4235-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="e4235-120">Gibt an, ob der Laufzeitstartcode, die Registrierung sucht, um die Common Language Runtime-Version zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="e4235-120">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|  
  
## <a name="safemode-attribute"></a><span data-ttu-id="e4235-121">Safemode-Attribut</span><span class="sxs-lookup"><span data-stu-id="e4235-121">safemode Attribute</span></span>  
  
|<span data-ttu-id="e4235-122">Wert</span><span class="sxs-lookup"><span data-stu-id="e4235-122">Value</span></span>|<span data-ttu-id="e4235-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e4235-123">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="e4235-124">Der Laufzeitstartcode sucht in der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="e4235-124">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="e4235-125">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="e4235-125">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="e4235-126">Der Laufzeitstartcode sucht nicht in der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="e4235-126">The runtime startup code does not look in the registry.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e4235-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e4235-127">Child Elements</span></span>  
 <span data-ttu-id="e4235-128">Keine</span><span class="sxs-lookup"><span data-stu-id="e4235-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e4235-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e4235-129">Parent Elements</span></span>  
  
|<span data-ttu-id="e4235-130">Element</span><span class="sxs-lookup"><span data-stu-id="e4235-130">Element</span></span>|<span data-ttu-id="e4235-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e4235-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e4235-132">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e4235-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`startup`|<span data-ttu-id="e4235-133">Enthält die `<requiredRuntime>` Element.</span><span class="sxs-lookup"><span data-stu-id="e4235-133">Contains the `<requiredRuntime>` element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4235-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e4235-134">Remarks</span></span>  
 <span data-ttu-id="e4235-135">Anwendungen, die nur Version 1.0 der Laufzeit unterstützen müssen verwenden die `<requiredRuntime>` Element.</span><span class="sxs-lookup"><span data-stu-id="e4235-135">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="e4235-136">Anwendungen, die mit Version 1.1 oder höher der Runtime erstellt müssen verwenden die `<supportedRuntime>` Element.</span><span class="sxs-lookup"><span data-stu-id="e4235-136">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4235-137">Bei Verwendung der [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) Funktion, um die Konfigurationsdatei angeben, müssen Sie die `<requiredRuntime>` -Element für alle Versionen der Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="e4235-137">If you use the [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="e4235-138">Die `<supportedRuntime>` Element wird ignoriert, wenn Sie [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span><span class="sxs-lookup"><span data-stu-id="e4235-138">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>  
  
 <span data-ttu-id="e4235-139">Die `version` Attributzeichenfolge muss die Installation Ordnernamen für die angegebene Version von .NET Framework entsprechen.</span><span class="sxs-lookup"><span data-stu-id="e4235-139">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="e4235-140">Diese Zeichenfolge wird nicht interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="e4235-140">This string is not interpreted.</span></span> <span data-ttu-id="e4235-141">Wenn der Laufzeitstartcode übereinstimmenden Ordner nicht gefunden wird, wird die Common Language Runtime nicht geladen. der Startcode zeigt eine Fehlermeldung an und beendet.</span><span class="sxs-lookup"><span data-stu-id="e4235-141">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e4235-142">Der Startcode für eine Anwendung, die in Microsoft Internet Explorer gehostet wird, ignoriert der `<requiredRuntime>` Element.</span><span class="sxs-lookup"><span data-stu-id="e4235-142">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4235-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e4235-143">Example</span></span>  
 <span data-ttu-id="e4235-144">Im folgende Beispiel wird gezeigt, wie die Common Language Runtime-Version in einer Konfigurationsdatei angegeben.</span><span class="sxs-lookup"><span data-stu-id="e4235-144">The following example shows how to specify the runtime version in a configuration file.</span></span>  
  
```xml  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e4235-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4235-145">See Also</span></span>  
 [<span data-ttu-id="e4235-146">Startup Settings Schema (Schema für Starteinstellungen)</span><span class="sxs-lookup"><span data-stu-id="e4235-146">Startup Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [<span data-ttu-id="e4235-147">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="e4235-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="e4235-148">\<PaveOver> Specifying Which Runtime Version to Use (Festlegen der zu verwendenden Runtimeversion)</span><span class="sxs-lookup"><span data-stu-id="e4235-148">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](http://msdn.microsoft.com/en-us/c376208d-980d-42b4-865b-fbe0d9cc97c2)
