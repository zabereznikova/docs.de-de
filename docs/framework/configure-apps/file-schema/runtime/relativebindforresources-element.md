---
title: <relativeBindForResources>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: daf576488e38bed28c7c0e5222bc053659372ff0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91184000"
---
# <a name="relativebindforresources-element"></a><span data-ttu-id="e74e0-102">\<relativeBindForResources>-Element</span><span class="sxs-lookup"><span data-stu-id="e74e0-102">\<relativeBindForResources> Element</span></span>

<span data-ttu-id="e74e0-103">Optimiert den Test für Satellitenassemblys.</span><span class="sxs-lookup"><span data-stu-id="e74e0-103">Optimizes the probe for satellite assemblies.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<relativeBindForResources>**  
  
## <a name="syntax"></a><span data-ttu-id="e74e0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e74e0-104">Syntax</span></span>  
  
```xml
<relativeBindForResources
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e74e0-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e74e0-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e74e0-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e74e0-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e74e0-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="e74e0-107">Attributes</span></span>  
  
|<span data-ttu-id="e74e0-108">attribute</span><span class="sxs-lookup"><span data-stu-id="e74e0-108">Attribute</span></span>|<span data-ttu-id="e74e0-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e74e0-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="e74e0-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="e74e0-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="e74e0-111">Gibt an, ob der Common Language Runtime den Test für Satellitenassemblys optimiert.</span><span class="sxs-lookup"><span data-stu-id="e74e0-111">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="e74e0-112">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="e74e0-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="e74e0-113">Wert</span><span class="sxs-lookup"><span data-stu-id="e74e0-113">Value</span></span>|<span data-ttu-id="e74e0-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e74e0-114">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="e74e0-115">Der Test für Satellitenassemblys wird von der Laufzeit nicht optimiert.</span><span class="sxs-lookup"><span data-stu-id="e74e0-115">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="e74e0-116">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="e74e0-116">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="e74e0-117">Die Laufzeit optimiert den Test für Satellitenassemblys.</span><span class="sxs-lookup"><span data-stu-id="e74e0-117">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e74e0-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e74e0-118">Child Elements</span></span>  

 <span data-ttu-id="e74e0-119">Keine</span><span class="sxs-lookup"><span data-stu-id="e74e0-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e74e0-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e74e0-120">Parent Elements</span></span>  
  
|<span data-ttu-id="e74e0-121">Element</span><span class="sxs-lookup"><span data-stu-id="e74e0-121">Element</span></span>|<span data-ttu-id="e74e0-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e74e0-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e74e0-123">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e74e0-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e74e0-124">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="e74e0-124">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e74e0-125">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e74e0-125">Remarks</span></span>  

 <span data-ttu-id="e74e0-126">Im allgemeinen Ressourcen-Manager Tests für Ressourcen durch, wie im Thema [Verpacken und](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) Bereitstellen von Ressourcen dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="e74e0-126">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="e74e0-127">Dies bedeutet Folgendes: Wenn Ressourcen-Manager eine bestimmte lokalisierte Version einer Ressource testet, kann Sie im globalen Assemblycache suchen, in einem kulturspezifischen Ordner in der Codebasis der Anwendung suchen, Windows Installer nach Satellitenassemblys Abfragen und das-Ereignis Auswerfen <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="e74e0-127">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="e74e0-128">Das- `<relativeBindForResources>` Element optimiert die Art und Weise, in der Ressourcen-Manager auf Satellitenassemblys prüft</span><span class="sxs-lookup"><span data-stu-id="e74e0-128">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="e74e0-129">Die Leistung kann bei der Überprüfung von Ressourcen unter den folgenden Bedingungen verbessert werden:</span><span class="sxs-lookup"><span data-stu-id="e74e0-129">It can improve performance when probing for resources under the following conditions:</span></span>  
  
- <span data-ttu-id="e74e0-130">Wenn die Satellitenassembly am gleichen Speicherort wie die Codeassembly bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e74e0-130">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="e74e0-131">Anders ausgedrückt: Wenn die Codeassembly im globalen Assemblycache installiert ist, müssen auch die Satellitenassemblys dort installiert werden.</span><span class="sxs-lookup"><span data-stu-id="e74e0-131">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="e74e0-132">Wenn die Codeassembly in der Codebasis der Anwendung installiert ist, müssen die Satellitenassemblys auch in einem kulturspezifischen Ordner in der Codebasis installiert werden.</span><span class="sxs-lookup"><span data-stu-id="e74e0-132">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
- <span data-ttu-id="e74e0-133">Wenn Windows Installer nicht verwendet wird oder nur selten für die Bedarfs gesteuerte Installation von Satellitenassemblys verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e74e0-133">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
- <span data-ttu-id="e74e0-134">Wenn der Anwendungscode das Ereignis nicht behandelt <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="e74e0-134">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="e74e0-135">`enabled`Wenn Sie das-Attribut des-Elements festlegen, wird der `<relativeBindForResources>` Ressourcen-Manager Test `true` für Satellitenassemblys wie folgt optimiert:</span><span class="sxs-lookup"><span data-stu-id="e74e0-135">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
- <span data-ttu-id="e74e0-136">Der Speicherort der übergeordneten Codeassembly wird verwendet, um nach der Satellitenassembly zu suchen.</span><span class="sxs-lookup"><span data-stu-id="e74e0-136">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
- <span data-ttu-id="e74e0-137">Windows Installer für Satellitenassemblys werden nicht abgefragt.</span><span class="sxs-lookup"><span data-stu-id="e74e0-137">It does not query Windows Installer for satellite assemblies.</span></span>  
  
- <span data-ttu-id="e74e0-138">Das-Ereignis wird nicht erhoben <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="e74e0-138">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e74e0-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e74e0-139">See also</span></span>

- [<span data-ttu-id="e74e0-140">Verpacken und Bereitstellen von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="e74e0-140">Packaging and Deploying Resources</span></span>](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [<span data-ttu-id="e74e0-141">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="e74e0-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e74e0-142">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="e74e0-142">Configuration File Schema</span></span>](../index.md)
