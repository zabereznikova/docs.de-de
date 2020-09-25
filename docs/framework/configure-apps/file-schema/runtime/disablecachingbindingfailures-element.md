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
ms.openlocfilehash: c9e608bfd54b641564a9095076455e10dd8653fb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176122"
---
# <a name="disablecachingbindingfailures-element"></a><span data-ttu-id="16669-102">\<disableCachingBindingFailures>-Element</span><span class="sxs-lookup"><span data-stu-id="16669-102">\<disableCachingBindingFailures> Element</span></span>

<span data-ttu-id="16669-103">Gibt an, ob das Zwischenspeichern von Bindungs Fehlern deaktiviert werden soll, die auftreten, da die Assembly nicht durchsuchen gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="16669-103">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<disableCachingBindingFailures>**  
  
## <a name="syntax"></a><span data-ttu-id="16669-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="16669-104">Syntax</span></span>  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="16669-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="16669-105">Attributes and Elements</span></span>  

 <span data-ttu-id="16669-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="16669-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="16669-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="16669-107">Attributes</span></span>  
  
|<span data-ttu-id="16669-108">attribute</span><span class="sxs-lookup"><span data-stu-id="16669-108">Attribute</span></span>|<span data-ttu-id="16669-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="16669-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="16669-110">enabled</span><span class="sxs-lookup"><span data-stu-id="16669-110">enabled</span></span>|<span data-ttu-id="16669-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="16669-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="16669-112">Gibt an, ob das Zwischenspeichern von Bindungs Fehlern deaktiviert werden soll, die auftreten, da die Assembly nicht durchsuchen gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="16669-112">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="16669-113">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="16669-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="16669-114">Wert</span><span class="sxs-lookup"><span data-stu-id="16669-114">Value</span></span>|<span data-ttu-id="16669-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16669-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="16669-116">0</span><span class="sxs-lookup"><span data-stu-id="16669-116">0</span></span>|<span data-ttu-id="16669-117">Deaktivieren Sie nicht das Zwischenspeichern von Bindungs Fehlern, die auftreten, da die Assembly nicht durchsuchen gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="16669-117">Do not disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="16669-118">Dies ist das Standard Bindungsverhalten, beginnend mit dem .NET Framework-Version 2,0.</span><span class="sxs-lookup"><span data-stu-id="16669-118">This is the default binding behavior starting with the .NET Framework version 2.0.</span></span>|  
|<span data-ttu-id="16669-119">1</span><span class="sxs-lookup"><span data-stu-id="16669-119">1</span></span>|<span data-ttu-id="16669-120">Hiermit deaktivieren Sie das Zwischenspeichern von Bindungs Fehlern, die auftreten, da die Assembly nicht durch Tests gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="16669-120">Disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="16669-121">Diese Einstellung kehrt zum Bindungsverhalten der .NET Framework Version 1,1 zurück.</span><span class="sxs-lookup"><span data-stu-id="16669-121">This setting reverts to the binding behavior of the .NET Framework version 1.1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="16669-122">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="16669-122">Child Elements</span></span>  

 <span data-ttu-id="16669-123">Keine</span><span class="sxs-lookup"><span data-stu-id="16669-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="16669-124">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="16669-124">Parent Elements</span></span>  
  
|<span data-ttu-id="16669-125">Element</span><span class="sxs-lookup"><span data-stu-id="16669-125">Element</span></span>|<span data-ttu-id="16669-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="16669-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="16669-127">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="16669-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="16669-128">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="16669-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16669-129">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="16669-129">Remarks</span></span>  

 <span data-ttu-id="16669-130">Beginnend mit der .NET Framework Version 2,0 besteht das Standardverhalten beim Laden von Assemblys darin, alle Bindungs-und Ladefehler zwischenzuspeichern.</span><span class="sxs-lookup"><span data-stu-id="16669-130">Starting with the .NET Framework version 2.0, the default behavior for loading assemblies is to cache all binding and loading failures.</span></span> <span data-ttu-id="16669-131">Das heißt, wenn ein Versuch, eine Assembly zu laden, fehlschlägt, schlagen nachfolgende Anforderungen zum Laden derselben Assembly sofort fehl, ohne dass versucht wird, die Assembly zu finden.</span><span class="sxs-lookup"><span data-stu-id="16669-131">That is, if an attempt to load an assembly fails, subsequent requests to load the same assembly fail immediately, without any attempt to locate the assembly.</span></span> <span data-ttu-id="16669-132">Dieses Element deaktiviert dieses Standardverhalten bei Bindungs Fehlern, die auftreten, da die Assembly nicht im Überprüfungs Pfad gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="16669-132">This element disables that default behavior for binding failures that occur because the assembly could not be found in the probing path.</span></span> <span data-ttu-id="16669-133">Diese Fehler lösen aus <xref:System.IO.FileNotFoundException> .</span><span class="sxs-lookup"><span data-stu-id="16669-133">These failures throw <xref:System.IO.FileNotFoundException>.</span></span>  
  
 <span data-ttu-id="16669-134">Einige Bindungs-und Ladefehler sind von diesem Element nicht betroffen und werden immer zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="16669-134">Some binding and loading failures are not affected by this element, and are always cached.</span></span> <span data-ttu-id="16669-135">Diese Fehler treten auf, weil die Assembly gefunden wurde, aber nicht geladen werden konnte.</span><span class="sxs-lookup"><span data-stu-id="16669-135">These failures occur because the assembly was found but could not be loaded.</span></span> <span data-ttu-id="16669-136">Sie lösen <xref:System.BadImageFormatException> oder aus <xref:System.IO.FileLoadException> .</span><span class="sxs-lookup"><span data-stu-id="16669-136">They throw <xref:System.BadImageFormatException> or <xref:System.IO.FileLoadException>.</span></span> <span data-ttu-id="16669-137">In der folgenden Liste sind einige Beispiele für derartige Fehler enthalten.</span><span class="sxs-lookup"><span data-stu-id="16669-137">The following list includes some examples of such failures.</span></span>  
  
- <span data-ttu-id="16669-138">Wenn Sie versuchen, eine Datei zu laden, ist keine gültige Assembly. nachfolgende Versuche, die Assembly zu laden, schlagen auch dann fehl, wenn die ungültige Datei durch die richtige Assembly ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="16669-138">If you attempt to load a file is not a valid assembly, subsequent attempts to load the assembly will fail even if the bad file is replaced with the correct assembly.</span></span>  
  
- <span data-ttu-id="16669-139">Wenn Sie versuchen, eine Assembly zu laden, die vom Dateisystem gesperrt ist, schlagen nachfolgende Versuche, die Assembly zu laden, auch dann fehl, wenn die Assembly vom Dateisystem freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="16669-139">If you attempt to load an assembly that is locked by the file system, subsequent attempts to load the assembly will fail even after the assembly is released by the file system.</span></span>  
  
- <span data-ttu-id="16669-140">Wenn sich eine oder mehrere Versionen der Assembly, die Sie laden möchten, im Überprüfungs Pfad befinden, die von Ihnen angeforderte Version jedoch nicht zu Ihnen gehört, schlagen nachfolgende Versuche, diese Version zu laden, auch dann fehl, wenn die richtige Version in den Überprüfungs Pfad verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="16669-140">If one or more versions of the assembly that you are attempting to load is in the probing path, but the specific version you are requesting is not among them, subsequent attempts to load that version will fail even if the correct version is moved into the probing path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16669-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="16669-141">Example</span></span>  

 <span data-ttu-id="16669-142">Das folgende Beispiel zeigt, wie Sie das Zwischenspeichern von Assemblybindungsfehlern deaktivieren, die auftreten, da die Assembly nicht durchsucht wurde.</span><span class="sxs-lookup"><span data-stu-id="16669-142">The following example shows how to disable the caching of assembly binding failures that occur because the assembly was not found by probing.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="16669-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="16669-143">See also</span></span>

- [<span data-ttu-id="16669-144">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="16669-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="16669-145">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="16669-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="16669-146">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="16669-146">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
