---
title: '&lt;RequiredRuntime&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 7cb5e29f3d7fc1faffdba01a5322f1883fca8af0
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47069699"
---
# <a name="ltrequiredruntimegt-element"></a><span data-ttu-id="14815-102">&lt;RequiredRuntime&gt; Element</span><span class="sxs-lookup"><span data-stu-id="14815-102">&lt;requiredRuntime&gt; Element</span></span>
<span data-ttu-id="14815-103">Gibt an, dass die Anwendung nur Version 1.0 der Common Language Runtime unterstützt.</span><span class="sxs-lookup"><span data-stu-id="14815-103">Specifies that the application supports only version 1.0 of the common language runtime.</span></span> <span data-ttu-id="14815-104">Dieses Element ist veraltet und sollte nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="14815-104">This element is deprecated and should no longer be used.</span></span> <span data-ttu-id="14815-105">Die [ `supportedRuntime` ](supportedruntime-element.md) Element sollte stattdessen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="14815-105">The [`supportedRuntime`](supportedruntime-element.md) element should be used instead.</span></span>
  
 <span data-ttu-id="14815-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="14815-106">\<configuration></span></span>  
<span data-ttu-id="14815-107">\<Startup ></span><span class="sxs-lookup"><span data-stu-id="14815-107">\<startup></span></span>  
<span data-ttu-id="14815-108">\<requiredRuntime></span><span class="sxs-lookup"><span data-stu-id="14815-108">\<requiredRuntime></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14815-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="14815-109">Syntax</span></span>  
  
```xml  
   <requiredRuntime    
version="runtime version"  
safemode="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="14815-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="14815-110">Attributes and Elements</span></span>  
 <span data-ttu-id="14815-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="14815-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="14815-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="14815-112">Attributes</span></span>  
  
|<span data-ttu-id="14815-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="14815-113">Attribute</span></span>|<span data-ttu-id="14815-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14815-114">Description</span></span>|  
|---------------|-----------------|  
|`version`|<span data-ttu-id="14815-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="14815-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="14815-116">Ein Zeichenfolgenwert, der angibt, die Version von .NET Framework, die diese Anwendung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="14815-116">A string value that specifies the version of the .NET Framework that this application supports.</span></span> <span data-ttu-id="14815-117">Der Zeichenfolgenwert muss den Namen des Verzeichnisses finden Sie unter dem Stamm der .NET Framework-Installation übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="14815-117">The string value must match the directory name found under the .NET Framework installation root.</span></span> <span data-ttu-id="14815-118">Der Inhalt des Zeichenfolgenwerts wird nicht analysiert.</span><span class="sxs-lookup"><span data-stu-id="14815-118">The contents of the string value are not parsed.</span></span>|  
|`safemode`|<span data-ttu-id="14815-119">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="14815-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="14815-120">Gibt an, ob die Common Language Runtime-Startcode die Registrierung zum Ermitteln der RuntimeVersion der Common Language durchsucht.</span><span class="sxs-lookup"><span data-stu-id="14815-120">Specifies whether the runtime startup code searches the registry to determine the runtime version.</span></span>|  
  
## <a name="safemode-attribute"></a><span data-ttu-id="14815-121">Safemode-Attribut</span><span class="sxs-lookup"><span data-stu-id="14815-121">safemode Attribute</span></span>  
  
|<span data-ttu-id="14815-122">Wert</span><span class="sxs-lookup"><span data-stu-id="14815-122">Value</span></span>|<span data-ttu-id="14815-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14815-123">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="14815-124">Der Startcode für die Common Language Runtime sucht in der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="14815-124">The runtime startup code looks in the registry.</span></span> <span data-ttu-id="14815-125">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="14815-125">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="14815-126">Der Laufzeitstartcode scheint sich nicht in der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="14815-126">The runtime startup code does not look in the registry.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="14815-127">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="14815-127">Child Elements</span></span>  
 <span data-ttu-id="14815-128">Keine</span><span class="sxs-lookup"><span data-stu-id="14815-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="14815-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="14815-129">Parent Elements</span></span>  
  
|<span data-ttu-id="14815-130">Element</span><span class="sxs-lookup"><span data-stu-id="14815-130">Element</span></span>|<span data-ttu-id="14815-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14815-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="14815-132">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="14815-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`startup`|<span data-ttu-id="14815-133">Enthält die `<requiredRuntime>` Element.</span><span class="sxs-lookup"><span data-stu-id="14815-133">Contains the `<requiredRuntime>` element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14815-134">Hinweise</span><span class="sxs-lookup"><span data-stu-id="14815-134">Remarks</span></span>  
 <span data-ttu-id="14815-135">Anwendungen, die nur in Version 1.0 von der Laufzeit nicht verwenden, müssen die `<requiredRuntime>` Element.</span><span class="sxs-lookup"><span data-stu-id="14815-135">Applications built to support only version 1.0 of the runtime must use the `<requiredRuntime>` element.</span></span> <span data-ttu-id="14815-136">Erstellen von Anwendungen mit Version 1.1 oder höher der Runtime verwenden, müssen die `<supportedRuntime>` Element.</span><span class="sxs-lookup"><span data-stu-id="14815-136">Applications built using version 1.1 or later of the runtime must use the `<supportedRuntime>` element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14815-137">Bei Verwendung der [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) Funktion, um die Konfigurationsdatei angeben, müssen Sie die `<requiredRuntime>` -Element für alle Versionen der Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="14815-137">If you use the [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md) function to specify the configuration file, you must use the `<requiredRuntime>` element for all versions of the runtime.</span></span> <span data-ttu-id="14815-138">Die `<supportedRuntime>` Element wird ignoriert, wenn Sie [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span><span class="sxs-lookup"><span data-stu-id="14815-138">The `<supportedRuntime>` element is ignored when you use [CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md).</span></span>  
  
 <span data-ttu-id="14815-139">Die `version` Attributzeichenfolge muss den Ordnernamen Installation, für die angegebene Version von .NET Framework entsprechen.</span><span class="sxs-lookup"><span data-stu-id="14815-139">The `version` attribute string must match the installation folder name for the specified version of the .NET Framework.</span></span> <span data-ttu-id="14815-140">Diese Zeichenfolge wird nicht interpretiert.</span><span class="sxs-lookup"><span data-stu-id="14815-140">This string is not interpreted.</span></span> <span data-ttu-id="14815-141">Wenn der Laufzeitstartcode einen entsprechenden Ordner nicht gefunden wird, ist die Runtime nicht geladen werden. der Startcode zeigt eine Fehlermeldung an und wird beendet.</span><span class="sxs-lookup"><span data-stu-id="14815-141">If the runtime startup code does not find a matching folder, the runtime is not loaded; the startup code shows an error message and quits.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14815-142">Der Startcode für eine Anwendung, die in Microsoft Internet Explorer gehostet wird, ignoriert der `<requiredRuntime>` Element.</span><span class="sxs-lookup"><span data-stu-id="14815-142">The startup code for an application that is hosted in Microsoft Internet Explorer ignores the `<requiredRuntime>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14815-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="14815-143">Example</span></span>  
 <span data-ttu-id="14815-144">Das folgende Beispiel zeigt, wie die Runtime-Version in einer Konfigurationsdatei angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="14815-144">The following example shows how to specify the runtime version in a configuration file.</span></span>  
  
```xml  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="14815-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14815-145">See Also</span></span>  
 [<span data-ttu-id="14815-146">Startup Settings Schema (Schema für Starteinstellungen)</span><span class="sxs-lookup"><span data-stu-id="14815-146">Startup Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [<span data-ttu-id="14815-147">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="14815-147">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="14815-148">\<PaveOver> Specifying Which Runtime Version to Use (Festlegen der zu verwendenden Runtimeversion)</span><span class="sxs-lookup"><span data-stu-id="14815-148">\<PaveOver> Specifying Which Runtime Version to Use</span></span>](https://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)
