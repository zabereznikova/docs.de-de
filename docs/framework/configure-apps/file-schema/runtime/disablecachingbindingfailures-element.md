---
title: <disableCachingBindingFailures>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCachingBindingFailures
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCachingBindingFailures
helpviewer_keywords:
- assemblies [.NET Framework],caching binding failures
- caching assembly binding failures
- <disableCachingBindingFailures> element
- disableCachingBindingFailures element
ms.assetid: bf598873-83b7-48de-8955-00b0504fbad0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4893adaf528f1a9ef8fc8eab8027406fd8520cc2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159275"
---
# <a name="disablecachingbindingfailures-element"></a><span data-ttu-id="7e1ef-102">\<DisableCachingBindingFailures >-Element</span><span class="sxs-lookup"><span data-stu-id="7e1ef-102">\<disableCachingBindingFailures> Element</span></span>
<span data-ttu-id="7e1ef-103">Gibt an, ob das Zwischenspeichern von Bindungsfehlern, die auftreten, da die Assembly nicht, durch die Überprüfung gefunden wurde zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="7e1ef-103">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>  
  
 <span data-ttu-id="7e1ef-104">\<Configuration >-Element</span><span class="sxs-lookup"><span data-stu-id="7e1ef-104">\<configuration> Element</span></span>  
<span data-ttu-id="7e1ef-105">\<Common Language Runtime >-Element</span><span class="sxs-lookup"><span data-stu-id="7e1ef-105">\<runtime> Element</span></span>  
<span data-ttu-id="7e1ef-106">\<disableCachingBindingFailures></span><span class="sxs-lookup"><span data-stu-id="7e1ef-106">\<disableCachingBindingFailures></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e1ef-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="7e1ef-107">Syntax</span></span>  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e1ef-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7e1ef-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7e1ef-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7e1ef-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e1ef-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="7e1ef-110">Attributes</span></span>  
  
|<span data-ttu-id="7e1ef-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="7e1ef-111">Attribute</span></span>|<span data-ttu-id="7e1ef-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e1ef-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7e1ef-113">enabled</span><span class="sxs-lookup"><span data-stu-id="7e1ef-113">enabled</span></span>|<span data-ttu-id="7e1ef-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="7e1ef-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="7e1ef-115">Gibt an, ob das Zwischenspeichern von Bindungsfehlern, die auftreten, da die Assembly nicht, durch die Überprüfung gefunden wurde zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="7e1ef-115">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="7e1ef-116">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="7e1ef-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="7e1ef-117">Wert</span><span class="sxs-lookup"><span data-stu-id="7e1ef-117">Value</span></span>|<span data-ttu-id="7e1ef-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e1ef-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7e1ef-119">0</span><span class="sxs-lookup"><span data-stu-id="7e1ef-119">0</span></span>|<span data-ttu-id="7e1ef-120">Deaktivieren Sie nicht das Zwischenspeichern von Bindungsfehlern, die auftreten, da die Assembly durch Testen nicht gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="7e1ef-120">Do not disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="7e1ef-121">Dies ist das Standardverhalten-Bindung ab .NET Framework, Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="7e1ef-121">This is the default binding behavior starting with the .NET Framework version 2.0.</span></span>|  
|<span data-ttu-id="7e1ef-122">1</span><span class="sxs-lookup"><span data-stu-id="7e1ef-122">1</span></span>|<span data-ttu-id="7e1ef-123">Deaktivieren Sie das Zwischenspeichern von Bindungsfehlern, die auftreten, da die Assembly durch Testen nicht gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="7e1ef-123">Disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="7e1ef-124">Diese Einstellung wird auf das Bindungsverhalten von .NET Framework, Version 1.1 zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="7e1ef-124">This setting reverts to the binding behavior of the .NET Framework version 1.1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e1ef-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7e1ef-125">Child Elements</span></span>  
 <span data-ttu-id="7e1ef-126">Keine</span><span class="sxs-lookup"><span data-stu-id="7e1ef-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7e1ef-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7e1ef-127">Parent Elements</span></span>  
  
|<span data-ttu-id="7e1ef-128">Element</span><span class="sxs-lookup"><span data-stu-id="7e1ef-128">Element</span></span>|<span data-ttu-id="7e1ef-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e1ef-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7e1ef-130">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="7e1ef-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="7e1ef-131">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="7e1ef-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e1ef-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7e1ef-132">Remarks</span></span>  
 <span data-ttu-id="7e1ef-133">Ab .NET Framework, Version 2.0, ist das Standardverhalten für das Laden von Assemblys zum Zwischenspeichern von alle Bindungs- und beim Laden von Fehlern.</span><span class="sxs-lookup"><span data-stu-id="7e1ef-133">Starting with the .NET Framework version 2.0, the default behavior for loading assemblies is to cache all binding and loading failures.</span></span> <span data-ttu-id="7e1ef-134">D. h. wenn Versuch zum Laden einer Assembly ein Fehler auftritt, ein Fehler auf nachfolgende Anforderungen zum Laden der gleichen Assembly sofort ohne zu versuchen, um die Assembly zu suchen.</span><span class="sxs-lookup"><span data-stu-id="7e1ef-134">That is, if an attempt to load an assembly fails, subsequent requests to load the same assembly fail immediately, without any attempt to locate the assembly.</span></span> <span data-ttu-id="7e1ef-135">Dieses Element deaktiviert, das Standardverhalten für die Bindung von Fehlern, die auftreten, da die Assembly nicht konnte, können Sie in den Suchpfad gefunden werden wird.</span><span class="sxs-lookup"><span data-stu-id="7e1ef-135">This element disables that default behavior for binding failures that occur because the assembly could not be found in the probing path.</span></span> <span data-ttu-id="7e1ef-136">Diese Fehler lösen <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="7e1ef-136">These failures throw <xref:System.IO.FileNotFoundException>.</span></span>  
  
 <span data-ttu-id="7e1ef-137">Eine Bindung von Ladefehlern sind von diesem Element nicht betroffen und werden immer zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="7e1ef-137">Some binding and loading failures are not affected by this element, and are always cached.</span></span> <span data-ttu-id="7e1ef-138">Diese Fehler auftreten, da die Assembly wurde gefunden, aber nicht geladen werden konnte.</span><span class="sxs-lookup"><span data-stu-id="7e1ef-138">These failures occur because the assembly was found but could not be loaded.</span></span> <span data-ttu-id="7e1ef-139">Sie lösen <xref:System.BadImageFormatException> oder <xref:System.IO.FileLoadException>.</span><span class="sxs-lookup"><span data-stu-id="7e1ef-139">They throw <xref:System.BadImageFormatException> or <xref:System.IO.FileLoadException>.</span></span> <span data-ttu-id="7e1ef-140">Die folgende Liste enthält einige Beispiele für solche Fehler.</span><span class="sxs-lookup"><span data-stu-id="7e1ef-140">The following list includes some examples of such failures.</span></span>  
  
-   <span data-ttu-id="7e1ef-141">Wenn Sie versuchen, das Laden eine Datei ist keine gültige Assembly, nachfolgende Versuche zum Laden der Assembly schlägt fehl, selbst wenn die ungültige Datei durch die richtige Assembly ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="7e1ef-141">If you attempt to load a file is not a valid assembly, subsequent attempts to load the assembly will fail even if the bad file is replaced with the correct assembly.</span></span>  
  
-   <span data-ttu-id="7e1ef-142">Wenn Sie versuchen, eine Assembly zu laden, die vom Dateisystem gesperrt ist, schlagen nachfolgende Versuche zum Laden der Assembly fehl, auch nach die Assembly durch das Dateisystem freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="7e1ef-142">If you attempt to load an assembly that is locked by the file system, subsequent attempts to load the assembly will fail even after the assembly is released by the file system.</span></span>  
  
-   <span data-ttu-id="7e1ef-143">Wenn eine oder mehrere Versionen der Assembly, die Sie laden möchten befindet sich in den Suchpfad, aber die die angeforderte Version nicht untereinander ist, fehl nachfolgende Versuche, diese Version zu laden, auch wenn die richtige Version in den Suchpfad verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="7e1ef-143">If one or more versions of the assembly that you are attempting to load is in the probing path, but the specific version you are requesting is not among them, subsequent attempts to load that version will fail even if the correct version is moved into the probing path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e1ef-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7e1ef-144">Example</span></span>  
 <span data-ttu-id="7e1ef-145">Das folgende Beispiel zeigt, wie das Zwischenspeichern von Assemblybindungsfehlern, die auftreten, da die Assembly nicht, durch die Überprüfung gefunden wurde zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="7e1ef-145">The following example shows how to disable the caching of assembly binding failures that occur because the assembly was not found by probing.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7e1ef-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e1ef-146">See also</span></span>

- [<span data-ttu-id="7e1ef-147">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="7e1ef-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="7e1ef-148">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="7e1ef-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="7e1ef-149">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="7e1ef-149">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
