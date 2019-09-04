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
ms.openlocfilehash: d5b45ea4b30677d17e72685b16c19f9192c8c144
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252683"
---
# <a name="disablecachingbindingfailures-element"></a><span data-ttu-id="89d36-102">\<disablecachingbindingfailure-> Element</span><span class="sxs-lookup"><span data-stu-id="89d36-102">\<disableCachingBindingFailures> Element</span></span>
<span data-ttu-id="89d36-103">Gibt an, ob das Zwischenspeichern von Bindungs Fehlern deaktiviert werden soll, die auftreten, da die Assembly nicht durchsuchen gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="89d36-103">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>  
  
<span data-ttu-id="89d36-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="89d36-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="89d36-105">&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="89d36-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="89d36-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<disableCachingBindingFailures>**</span><span class="sxs-lookup"><span data-stu-id="89d36-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<disableCachingBindingFailures>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89d36-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="89d36-107">Syntax</span></span>  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89d36-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="89d36-108">Attributes and Elements</span></span>  
 <span data-ttu-id="89d36-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="89d36-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89d36-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="89d36-110">Attributes</span></span>  
  
|<span data-ttu-id="89d36-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="89d36-111">Attribute</span></span>|<span data-ttu-id="89d36-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89d36-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="89d36-113">enabled</span><span class="sxs-lookup"><span data-stu-id="89d36-113">enabled</span></span>|<span data-ttu-id="89d36-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="89d36-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="89d36-115">Gibt an, ob das Zwischenspeichern von Bindungs Fehlern deaktiviert werden soll, die auftreten, da die Assembly nicht durchsuchen gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="89d36-115">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="89d36-116">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="89d36-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="89d36-117">Wert</span><span class="sxs-lookup"><span data-stu-id="89d36-117">Value</span></span>|<span data-ttu-id="89d36-118">Description</span><span class="sxs-lookup"><span data-stu-id="89d36-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="89d36-119">0</span><span class="sxs-lookup"><span data-stu-id="89d36-119">0</span></span>|<span data-ttu-id="89d36-120">Deaktivieren Sie nicht das Zwischenspeichern von Bindungs Fehlern, die auftreten, da die Assembly nicht durchsuchen gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="89d36-120">Do not disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="89d36-121">Dies ist das Standard Bindungsverhalten, beginnend mit dem .NET Framework-Version 2,0.</span><span class="sxs-lookup"><span data-stu-id="89d36-121">This is the default binding behavior starting with the .NET Framework version 2.0.</span></span>|  
|<span data-ttu-id="89d36-122">1</span><span class="sxs-lookup"><span data-stu-id="89d36-122">1</span></span>|<span data-ttu-id="89d36-123">Hiermit deaktivieren Sie das Zwischenspeichern von Bindungs Fehlern, die auftreten, da die Assembly nicht durch Tests gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="89d36-123">Disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="89d36-124">Diese Einstellung kehrt zum Bindungsverhalten der .NET Framework Version 1,1 zurück.</span><span class="sxs-lookup"><span data-stu-id="89d36-124">This setting reverts to the binding behavior of the .NET Framework version 1.1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="89d36-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="89d36-125">Child Elements</span></span>  
 <span data-ttu-id="89d36-126">Keine</span><span class="sxs-lookup"><span data-stu-id="89d36-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="89d36-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="89d36-127">Parent Elements</span></span>  
  
|<span data-ttu-id="89d36-128">Element</span><span class="sxs-lookup"><span data-stu-id="89d36-128">Element</span></span>|<span data-ttu-id="89d36-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89d36-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="89d36-130">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="89d36-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="89d36-131">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="89d36-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89d36-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="89d36-132">Remarks</span></span>  
 <span data-ttu-id="89d36-133">Beginnend mit der .NET Framework Version 2,0 besteht das Standardverhalten beim Laden von Assemblys darin, alle Bindungs-und Ladefehler zwischenzuspeichern.</span><span class="sxs-lookup"><span data-stu-id="89d36-133">Starting with the .NET Framework version 2.0, the default behavior for loading assemblies is to cache all binding and loading failures.</span></span> <span data-ttu-id="89d36-134">Das heißt, wenn ein Versuch, eine Assembly zu laden, fehlschlägt, schlagen nachfolgende Anforderungen zum Laden derselben Assembly sofort fehl, ohne dass versucht wird, die Assembly zu finden.</span><span class="sxs-lookup"><span data-stu-id="89d36-134">That is, if an attempt to load an assembly fails, subsequent requests to load the same assembly fail immediately, without any attempt to locate the assembly.</span></span> <span data-ttu-id="89d36-135">Dieses Element deaktiviert dieses Standardverhalten bei Bindungs Fehlern, die auftreten, da die Assembly nicht im Überprüfungs Pfad gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="89d36-135">This element disables that default behavior for binding failures that occur because the assembly could not be found in the probing path.</span></span> <span data-ttu-id="89d36-136">Diese Fehler <xref:System.IO.FileNotFoundException>lösen aus.</span><span class="sxs-lookup"><span data-stu-id="89d36-136">These failures throw <xref:System.IO.FileNotFoundException>.</span></span>  
  
 <span data-ttu-id="89d36-137">Einige Bindungs-und Ladefehler sind von diesem Element nicht betroffen und werden immer zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="89d36-137">Some binding and loading failures are not affected by this element, and are always cached.</span></span> <span data-ttu-id="89d36-138">Diese Fehler treten auf, weil die Assembly gefunden wurde, aber nicht geladen werden konnte.</span><span class="sxs-lookup"><span data-stu-id="89d36-138">These failures occur because the assembly was found but could not be loaded.</span></span> <span data-ttu-id="89d36-139">Sie lösen <xref:System.IO.FileLoadException>oderaus. <xref:System.BadImageFormatException></span><span class="sxs-lookup"><span data-stu-id="89d36-139">They throw <xref:System.BadImageFormatException> or <xref:System.IO.FileLoadException>.</span></span> <span data-ttu-id="89d36-140">In der folgenden Liste sind einige Beispiele für derartige Fehler enthalten.</span><span class="sxs-lookup"><span data-stu-id="89d36-140">The following list includes some examples of such failures.</span></span>  
  
- <span data-ttu-id="89d36-141">Wenn Sie versuchen, eine Datei zu laden, ist keine gültige Assembly. nachfolgende Versuche, die Assembly zu laden, schlagen auch dann fehl, wenn die ungültige Datei durch die richtige Assembly ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="89d36-141">If you attempt to load a file is not a valid assembly, subsequent attempts to load the assembly will fail even if the bad file is replaced with the correct assembly.</span></span>  
  
- <span data-ttu-id="89d36-142">Wenn Sie versuchen, eine Assembly zu laden, die vom Dateisystem gesperrt ist, schlagen nachfolgende Versuche, die Assembly zu laden, auch dann fehl, wenn die Assembly vom Dateisystem freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="89d36-142">If you attempt to load an assembly that is locked by the file system, subsequent attempts to load the assembly will fail even after the assembly is released by the file system.</span></span>  
  
- <span data-ttu-id="89d36-143">Wenn sich eine oder mehrere Versionen der Assembly, die Sie laden möchten, im Überprüfungs Pfad befinden, die von Ihnen angeforderte Version jedoch nicht zu Ihnen gehört, schlagen nachfolgende Versuche, diese Version zu laden, auch dann fehl, wenn die richtige Version in den Überprüfungs Pfad verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="89d36-143">If one or more versions of the assembly that you are attempting to load is in the probing path, but the specific version you are requesting is not among them, subsequent attempts to load that version will fail even if the correct version is moved into the probing path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89d36-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89d36-144">Example</span></span>  
 <span data-ttu-id="89d36-145">Das folgende Beispiel zeigt, wie Sie das Zwischenspeichern von Assemblybindungsfehlern deaktivieren, die auftreten, da die Assembly nicht durchsucht wurde.</span><span class="sxs-lookup"><span data-stu-id="89d36-145">The following example shows how to disable the caching of assembly binding failures that occur because the assembly was not found by probing.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="89d36-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89d36-146">See also</span></span>

- [<span data-ttu-id="89d36-147">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="89d36-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="89d36-148">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="89d36-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="89d36-149">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="89d36-149">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
