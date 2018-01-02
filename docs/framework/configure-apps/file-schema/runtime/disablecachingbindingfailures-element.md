---
title: '&lt;DisableCachingBindingFailures&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCachingBindingFailures
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCachingBindingFailures
helpviewer_keywords:
- assemblies [.NET Framework],caching binding failures
- caching assembly binding failures
- <disableCachingBindingFailures> element
- disableCachingBindingFailures element
ms.assetid: bf598873-83b7-48de-8955-00b0504fbad0
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dd86bc2f58bc216f741c32a51925d3f4f8ef47df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltdisablecachingbindingfailuresgt-element"></a><span data-ttu-id="65489-102">&lt;DisableCachingBindingFailures&gt; Element</span><span class="sxs-lookup"><span data-stu-id="65489-102">&lt;disableCachingBindingFailures&gt; Element</span></span>
<span data-ttu-id="65489-103">Gibt an, ob das Zwischenspeichern von Assemblybindungsfehlern, die auftreten, da die Assembly nicht, durch die Überprüfung gefunden wurde zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="65489-103">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>  
  
 <span data-ttu-id="65489-104">\<Konfiguration >-Element</span><span class="sxs-lookup"><span data-stu-id="65489-104">\<configuration> Element</span></span>  
<span data-ttu-id="65489-105">\<Common Language Runtime >-Element</span><span class="sxs-lookup"><span data-stu-id="65489-105">\<runtime> Element</span></span>  
<span data-ttu-id="65489-106">\<DisableCachingBindingFailures ></span><span class="sxs-lookup"><span data-stu-id="65489-106">\<disableCachingBindingFailures></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65489-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="65489-107">Syntax</span></span>  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="65489-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="65489-108">Attributes and Elements</span></span>  
 <span data-ttu-id="65489-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="65489-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="65489-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="65489-110">Attributes</span></span>  
  
|<span data-ttu-id="65489-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="65489-111">Attribute</span></span>|<span data-ttu-id="65489-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="65489-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="65489-113">enabled</span><span class="sxs-lookup"><span data-stu-id="65489-113">enabled</span></span>|<span data-ttu-id="65489-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="65489-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="65489-115">Gibt an, ob das Zwischenspeichern von Assemblybindungsfehlern, die auftreten, da die Assembly nicht, durch die Überprüfung gefunden wurde zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="65489-115">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="65489-116">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="65489-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="65489-117">Wert</span><span class="sxs-lookup"><span data-stu-id="65489-117">Value</span></span>|<span data-ttu-id="65489-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="65489-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="65489-119">0</span><span class="sxs-lookup"><span data-stu-id="65489-119">0</span></span>|<span data-ttu-id="65489-120">Deaktivieren Sie nicht das Zwischenspeichern von Assemblybindungsfehlern, die auftreten, da die Assembly durch die Überprüfung nicht gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="65489-120">Do not disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="65489-121">Dies ist das Standardverhalten-Bindung beginnend mit .NET Framework, Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="65489-121">This is the default binding behavior starting with the .NET Framework version 2.0.</span></span>|  
|<span data-ttu-id="65489-122">1</span><span class="sxs-lookup"><span data-stu-id="65489-122">1</span></span>|<span data-ttu-id="65489-123">Deaktivieren Sie das Zwischenspeichern von Assemblybindungsfehlern, die auftreten, da die Assembly durch die Überprüfung nicht gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="65489-123">Disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="65489-124">Diese Einstellung zurücksetzt, das Bindungsverhalten von .NET Framework, Version 1.1.</span><span class="sxs-lookup"><span data-stu-id="65489-124">This setting reverts to the binding behavior of the .NET Framework version 1.1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="65489-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="65489-125">Child Elements</span></span>  
 <span data-ttu-id="65489-126">Keine</span><span class="sxs-lookup"><span data-stu-id="65489-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="65489-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="65489-127">Parent Elements</span></span>  
  
|<span data-ttu-id="65489-128">Element</span><span class="sxs-lookup"><span data-stu-id="65489-128">Element</span></span>|<span data-ttu-id="65489-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="65489-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="65489-130">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="65489-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="65489-131">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="65489-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65489-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="65489-132">Remarks</span></span>  
 <span data-ttu-id="65489-133">Beginnend mit .NET Framework, Version 2.0, ist das Standardverhalten für das Laden von Assemblys zum Zwischenspeichern aller binden und Laden von Fehlern.</span><span class="sxs-lookup"><span data-stu-id="65489-133">Starting with the .NET Framework version 2.0, the default behavior for loading assemblies is to cache all binding and loading failures.</span></span> <span data-ttu-id="65489-134">D. h., wenn ein Versuch zum Laden einer Assembly fehlschlägt, fehlschlagen, nachfolgende Anforderungen zum Laden der gleichen Assembly sofort ohne jeder Versuch, die Assembly gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="65489-134">That is, if an attempt to load an assembly fails, subsequent requests to load the same assembly fail immediately, without any attempt to locate the assembly.</span></span> <span data-ttu-id="65489-135">Dieses Element deaktiviert das Standardverhalten zum Binden von Fehlern, die auftreten, da die Assembly nicht im Überprüfungspfad gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="65489-135">This element disables that default behavior for binding failures that occur because the assembly could not be found in the probing path.</span></span> <span data-ttu-id="65489-136">Diese Fehler auslösen <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="65489-136">These failures throw <xref:System.IO.FileNotFoundException>.</span></span>  
  
 <span data-ttu-id="65489-137">Einige binden und Laden von Fehlern sind nicht betroffen von diesem Element und immer zwischengespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="65489-137">Some binding and loading failures are not affected by this element, and are always cached.</span></span> <span data-ttu-id="65489-138">Diese Fehler auftreten, da die Assembly wurde gefunden, aber nicht geladen werden konnte.</span><span class="sxs-lookup"><span data-stu-id="65489-138">These failures occur because the assembly was found but could not be loaded.</span></span> <span data-ttu-id="65489-139">Sie lösen <xref:System.BadImageFormatException> oder <xref:System.IO.FileLoadException>.</span><span class="sxs-lookup"><span data-stu-id="65489-139">They throw <xref:System.BadImageFormatException> or <xref:System.IO.FileLoadException>.</span></span> <span data-ttu-id="65489-140">Die folgende Liste enthält einige Beispiele für solche Fehler.</span><span class="sxs-lookup"><span data-stu-id="65489-140">The following list includes some examples of such failures.</span></span>  
  
-   <span data-ttu-id="65489-141">Wenn Sie versuchen, Sie laden eine Datei ist keine gültige Assembly, nachfolgende Versuche zum Laden der Assembly schlägt fehl, selbst wenn die ungültige Datei durch die richtige Assembly ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="65489-141">If you attempt to load a file is not a valid assembly, subsequent attempts to load the assembly will fail even if the bad file is replaced with the correct assembly.</span></span>  
  
-   <span data-ttu-id="65489-142">Wenn Sie versuchen, eine Assembly zu laden, die durch das Dateisystem gesperrt ist, schlagen nachfolgende Versuche zum Laden der Assembly fehl, auch nachdem die Assembly vom Dateisystem freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="65489-142">If you attempt to load an assembly that is locked by the file system, subsequent attempts to load the assembly will fail even after the assembly is released by the file system.</span></span>  
  
-   <span data-ttu-id="65489-143">Wenn eine oder mehrere Versionen der Assembly, die Sie laden möchten befindet sich in der Überprüfungspfad, aber die auf die angeforderte Version nicht untereinander ist, fehl nachfolgende Versuche, diese Version zu laden, auch wenn die richtige Version in den Suchpfad verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="65489-143">If one or more versions of the assembly that you are attempting to load is in the probing path, but the specific version you are requesting is not among them, subsequent attempts to load that version will fail even if the correct version is moved into the probing path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65489-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="65489-144">Example</span></span>  
 <span data-ttu-id="65489-145">Im folgende Beispiel veranschaulicht das Zwischenspeichern von Assemblybindungsfehlern, die auftreten, da die Assembly nicht, durch die Überprüfung gefunden wurde zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="65489-145">The following example shows how to disable the caching of assembly binding failures that occur because the assembly was not found by probing.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="65489-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65489-146">See Also</span></span>  
 [<span data-ttu-id="65489-147">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="65489-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="65489-148">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="65489-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="65489-149">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="65489-149">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
