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
ms.openlocfilehash: 23633cb282b8e59b4df4bcc2cd38717d805a207e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73117497"
---
# <a name="disablecachingbindingfailures-element"></a><span data-ttu-id="005e1-102">\<disablecachingbindingfailure >-Element</span><span class="sxs-lookup"><span data-stu-id="005e1-102">\<disableCachingBindingFailures> Element</span></span>
<span data-ttu-id="005e1-103">Gibt an, ob das Zwischenspeichern von Bindungs Fehlern deaktiviert werden soll, die auftreten, da die Assembly nicht durchsuchen gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="005e1-103">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>  
  
<span data-ttu-id="005e1-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="005e1-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="005e1-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="005e1-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="005e1-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<disablecachingbindingfailure >**</span><span class="sxs-lookup"><span data-stu-id="005e1-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<disableCachingBindingFailures>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="005e1-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="005e1-107">Syntax</span></span>  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="005e1-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="005e1-108">Attributes and Elements</span></span>  
 <span data-ttu-id="005e1-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="005e1-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="005e1-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="005e1-110">Attributes</span></span>  
  
|<span data-ttu-id="005e1-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="005e1-111">Attribute</span></span>|<span data-ttu-id="005e1-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="005e1-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="005e1-113">enabled</span><span class="sxs-lookup"><span data-stu-id="005e1-113">enabled</span></span>|<span data-ttu-id="005e1-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="005e1-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="005e1-115">Gibt an, ob das Zwischenspeichern von Bindungs Fehlern deaktiviert werden soll, die auftreten, da die Assembly nicht durchsuchen gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="005e1-115">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="005e1-116">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="005e1-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="005e1-117">Wert</span><span class="sxs-lookup"><span data-stu-id="005e1-117">Value</span></span>|<span data-ttu-id="005e1-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="005e1-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="005e1-119">0</span><span class="sxs-lookup"><span data-stu-id="005e1-119">0</span></span>|<span data-ttu-id="005e1-120">Deaktivieren Sie nicht das Zwischenspeichern von Bindungs Fehlern, die auftreten, da die Assembly nicht durchsuchen gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="005e1-120">Do not disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="005e1-121">Dies ist das Standard Bindungsverhalten, beginnend mit dem .NET Framework-Version 2,0.</span><span class="sxs-lookup"><span data-stu-id="005e1-121">This is the default binding behavior starting with the .NET Framework version 2.0.</span></span>|  
|<span data-ttu-id="005e1-122">1</span><span class="sxs-lookup"><span data-stu-id="005e1-122">1</span></span>|<span data-ttu-id="005e1-123">Hiermit deaktivieren Sie das Zwischenspeichern von Bindungs Fehlern, die auftreten, da die Assembly nicht durch Tests gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="005e1-123">Disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="005e1-124">Diese Einstellung kehrt zum Bindungsverhalten der .NET Framework Version 1,1 zurück.</span><span class="sxs-lookup"><span data-stu-id="005e1-124">This setting reverts to the binding behavior of the .NET Framework version 1.1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="005e1-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="005e1-125">Child Elements</span></span>  
 <span data-ttu-id="005e1-126">Keine</span><span class="sxs-lookup"><span data-stu-id="005e1-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="005e1-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="005e1-127">Parent Elements</span></span>  
  
|<span data-ttu-id="005e1-128">Element</span><span class="sxs-lookup"><span data-stu-id="005e1-128">Element</span></span>|<span data-ttu-id="005e1-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="005e1-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="005e1-130">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="005e1-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="005e1-131">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="005e1-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="005e1-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="005e1-132">Remarks</span></span>  
 <span data-ttu-id="005e1-133">Beginnend mit der .NET Framework Version 2,0 besteht das Standardverhalten beim Laden von Assemblys darin, alle Bindungs-und Ladefehler zwischenzuspeichern.</span><span class="sxs-lookup"><span data-stu-id="005e1-133">Starting with the .NET Framework version 2.0, the default behavior for loading assemblies is to cache all binding and loading failures.</span></span> <span data-ttu-id="005e1-134">Das heißt, wenn ein Versuch, eine Assembly zu laden, fehlschlägt, schlagen nachfolgende Anforderungen zum Laden derselben Assembly sofort fehl, ohne dass versucht wird, die Assembly zu finden.</span><span class="sxs-lookup"><span data-stu-id="005e1-134">That is, if an attempt to load an assembly fails, subsequent requests to load the same assembly fail immediately, without any attempt to locate the assembly.</span></span> <span data-ttu-id="005e1-135">Dieses Element deaktiviert dieses Standardverhalten bei Bindungs Fehlern, die auftreten, da die Assembly nicht im Überprüfungs Pfad gefunden werden konnte.</span><span class="sxs-lookup"><span data-stu-id="005e1-135">This element disables that default behavior for binding failures that occur because the assembly could not be found in the probing path.</span></span> <span data-ttu-id="005e1-136">Diese Fehler lösen <xref:System.IO.FileNotFoundException>aus.</span><span class="sxs-lookup"><span data-stu-id="005e1-136">These failures throw <xref:System.IO.FileNotFoundException>.</span></span>  
  
 <span data-ttu-id="005e1-137">Einige Bindungs-und Ladefehler sind von diesem Element nicht betroffen und werden immer zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="005e1-137">Some binding and loading failures are not affected by this element, and are always cached.</span></span> <span data-ttu-id="005e1-138">Diese Fehler treten auf, weil die Assembly gefunden wurde, aber nicht geladen werden konnte.</span><span class="sxs-lookup"><span data-stu-id="005e1-138">These failures occur because the assembly was found but could not be loaded.</span></span> <span data-ttu-id="005e1-139">Sie lösen <xref:System.BadImageFormatException> oder <xref:System.IO.FileLoadException>aus.</span><span class="sxs-lookup"><span data-stu-id="005e1-139">They throw <xref:System.BadImageFormatException> or <xref:System.IO.FileLoadException>.</span></span> <span data-ttu-id="005e1-140">In der folgenden Liste sind einige Beispiele für derartige Fehler enthalten.</span><span class="sxs-lookup"><span data-stu-id="005e1-140">The following list includes some examples of such failures.</span></span>  
  
- <span data-ttu-id="005e1-141">Wenn Sie versuchen, eine Datei zu laden, ist keine gültige Assembly. nachfolgende Versuche, die Assembly zu laden, schlagen auch dann fehl, wenn die ungültige Datei durch die richtige Assembly ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="005e1-141">If you attempt to load a file is not a valid assembly, subsequent attempts to load the assembly will fail even if the bad file is replaced with the correct assembly.</span></span>  
  
- <span data-ttu-id="005e1-142">Wenn Sie versuchen, eine Assembly zu laden, die vom Dateisystem gesperrt ist, schlagen nachfolgende Versuche, die Assembly zu laden, auch dann fehl, wenn die Assembly vom Dateisystem freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="005e1-142">If you attempt to load an assembly that is locked by the file system, subsequent attempts to load the assembly will fail even after the assembly is released by the file system.</span></span>  
  
- <span data-ttu-id="005e1-143">Wenn sich eine oder mehrere Versionen der Assembly, die Sie laden möchten, im Überprüfungs Pfad befinden, die von Ihnen angeforderte Version jedoch nicht zu Ihnen gehört, schlagen nachfolgende Versuche, diese Version zu laden, auch dann fehl, wenn die richtige Version in den Überprüfungs Pfad verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="005e1-143">If one or more versions of the assembly that you are attempting to load is in the probing path, but the specific version you are requesting is not among them, subsequent attempts to load that version will fail even if the correct version is moved into the probing path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="005e1-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="005e1-144">Example</span></span>  
 <span data-ttu-id="005e1-145">Das folgende Beispiel zeigt, wie Sie das Zwischenspeichern von Assemblybindungsfehlern deaktivieren, die auftreten, da die Assembly nicht durchsucht wurde.</span><span class="sxs-lookup"><span data-stu-id="005e1-145">The following example shows how to disable the caching of assembly binding failures that occur because the assembly was not found by probing.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="005e1-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="005e1-146">See also</span></span>

- [<span data-ttu-id="005e1-147">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="005e1-147">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="005e1-148">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="005e1-148">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="005e1-149">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="005e1-149">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
