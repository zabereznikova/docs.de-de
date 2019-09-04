---
title: <relativeBindForResources>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1ac2900707ddb39c62b34b0ebfbc4547cdd2653
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252348"
---
# <a name="relativebindforresources-element"></a><span data-ttu-id="500e0-102">\<relativebindforresources-> Element</span><span class="sxs-lookup"><span data-stu-id="500e0-102">\<relativeBindForResources> Element</span></span>
<span data-ttu-id="500e0-103">Optimiert den Test für Satellitenassemblys.</span><span class="sxs-lookup"><span data-stu-id="500e0-103">Optimizes the probe for satellite assemblies.</span></span>  
  
<span data-ttu-id="500e0-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="500e0-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="500e0-105">&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="500e0-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="500e0-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<relativeBindForResources>**</span><span class="sxs-lookup"><span data-stu-id="500e0-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<relativeBindForResources>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="500e0-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="500e0-107">Syntax</span></span>  
  
```xml
<relativeBindForResources    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="500e0-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="500e0-108">Attributes and Elements</span></span>  
 <span data-ttu-id="500e0-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="500e0-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="500e0-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="500e0-110">Attributes</span></span>  
  
|<span data-ttu-id="500e0-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="500e0-111">Attribute</span></span>|<span data-ttu-id="500e0-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="500e0-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="500e0-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="500e0-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="500e0-114">Gibt an, ob der Common Language Runtime den Test für Satellitenassemblys optimiert.</span><span class="sxs-lookup"><span data-stu-id="500e0-114">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="500e0-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="500e0-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="500e0-116">Wert</span><span class="sxs-lookup"><span data-stu-id="500e0-116">Value</span></span>|<span data-ttu-id="500e0-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="500e0-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="500e0-118">Der Test für Satellitenassemblys wird von der Laufzeit nicht optimiert.</span><span class="sxs-lookup"><span data-stu-id="500e0-118">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="500e0-119">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="500e0-119">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="500e0-120">Die Laufzeit optimiert den Test für Satellitenassemblys.</span><span class="sxs-lookup"><span data-stu-id="500e0-120">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="500e0-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="500e0-121">Child Elements</span></span>  
 <span data-ttu-id="500e0-122">Keine</span><span class="sxs-lookup"><span data-stu-id="500e0-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="500e0-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="500e0-123">Parent Elements</span></span>  
  
|<span data-ttu-id="500e0-124">Element</span><span class="sxs-lookup"><span data-stu-id="500e0-124">Element</span></span>|<span data-ttu-id="500e0-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="500e0-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="500e0-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="500e0-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="500e0-127">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="500e0-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="500e0-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="500e0-128">Remarks</span></span>  
 <span data-ttu-id="500e0-129">Im allgemeinen Ressourcen-Manager Tests für Ressourcen durch, wie im Thema [Verpacken und](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) Bereitstellen von Ressourcen dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="500e0-129">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="500e0-130">Dies bedeutet, dass beim Ressourcen-Manager von Tests für eine bestimmte lokalisierte Version einer Ressource möglicherweise im globalen Assemblycache gesucht wird, in einem kulturspezifischen Ordner in der Codebasis der Anwendung gesucht wird, Windows Installer nach Satellitenassemblys abgefragt wird und das <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> -Ereignis.</span><span class="sxs-lookup"><span data-stu-id="500e0-130">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="500e0-131">Das `<relativeBindForResources>` -Element optimiert die Art und Weise, in der Ressourcen-Manager auf Satellitenassemblys prüft</span><span class="sxs-lookup"><span data-stu-id="500e0-131">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="500e0-132">Die Leistung kann bei der Überprüfung von Ressourcen unter den folgenden Bedingungen verbessert werden:</span><span class="sxs-lookup"><span data-stu-id="500e0-132">It can improve performance when probing for resources under the following conditions:</span></span>  
  
- <span data-ttu-id="500e0-133">Wenn die Satellitenassembly am gleichen Speicherort wie die Codeassembly bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="500e0-133">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="500e0-134">Anders ausgedrückt: Wenn die Codeassembly im globalen Assemblycache installiert ist, müssen auch die Satellitenassemblys dort installiert werden.</span><span class="sxs-lookup"><span data-stu-id="500e0-134">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="500e0-135">Wenn die Codeassembly in der Codebasis der Anwendung installiert ist, müssen die Satellitenassemblys auch in einem kulturspezifischen Ordner in der Codebasis installiert werden.</span><span class="sxs-lookup"><span data-stu-id="500e0-135">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
- <span data-ttu-id="500e0-136">Wenn Windows Installer nicht verwendet wird oder nur selten für die Bedarfs gesteuerte Installation von Satellitenassemblys verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="500e0-136">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
- <span data-ttu-id="500e0-137">Wenn der Anwendungscode das <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> Ereignis nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="500e0-137">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="500e0-138">Wenn Sie `enabled` das-Attribut `<relativeBindForResources>` des- `true` Elements festlegen, wird der Ressourcen-Manager Test für Satellitenassemblys wie folgt optimiert:</span><span class="sxs-lookup"><span data-stu-id="500e0-138">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
- <span data-ttu-id="500e0-139">Der Speicherort der übergeordneten Codeassembly wird verwendet, um nach der Satellitenassembly zu suchen.</span><span class="sxs-lookup"><span data-stu-id="500e0-139">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
- <span data-ttu-id="500e0-140">Windows Installer für Satellitenassemblys werden nicht abgefragt.</span><span class="sxs-lookup"><span data-stu-id="500e0-140">It does not query Windows Installer for satellite assemblies.</span></span>  
  
- <span data-ttu-id="500e0-141">Das <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> -Ereignis wird nicht erhoben.</span><span class="sxs-lookup"><span data-stu-id="500e0-141">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="500e0-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="500e0-142">See also</span></span>

- [<span data-ttu-id="500e0-143">Verpacken und Bereitstellen von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="500e0-143">Packaging and Deploying Resources</span></span>](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [<span data-ttu-id="500e0-144">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="500e0-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="500e0-145">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="500e0-145">Configuration File Schema</span></span>](../index.md)
