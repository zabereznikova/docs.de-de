---
title: <relativeBindForResources>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- RelativeBindForResources element
- <relativeBindForResources> element
ms.assetid: 846ffa47-7257-4ce3-8cac-7ff627e0e34f
ms.openlocfilehash: cd49d424019a4e8422fee0ae16217d49cfc456b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153905"
---
# <a name="relativebindforresources-element"></a><span data-ttu-id="cca5c-102">\<relativeBindForResources> Element</span><span class="sxs-lookup"><span data-stu-id="cca5c-102">\<relativeBindForResources> Element</span></span>
<span data-ttu-id="cca5c-103">Optimiert den Test für Satellitenassemblys.</span><span class="sxs-lookup"><span data-stu-id="cca5c-103">Optimizes the probe for satellite assemblies.</span></span>  
  
<span data-ttu-id="cca5c-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="cca5c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="cca5c-105">&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="cca5c-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="cca5c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<relativeBindForResources>**</span><span class="sxs-lookup"><span data-stu-id="cca5c-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<relativeBindForResources>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cca5c-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="cca5c-107">Syntax</span></span>  
  
```xml
<relativeBindForResources
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cca5c-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cca5c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cca5c-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cca5c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cca5c-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="cca5c-110">Attributes</span></span>  
  
|<span data-ttu-id="cca5c-111">attribute</span><span class="sxs-lookup"><span data-stu-id="cca5c-111">Attribute</span></span>|<span data-ttu-id="cca5c-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cca5c-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="cca5c-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="cca5c-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="cca5c-114">Gibt an, ob die Common Language Runtime den Prüfpunkt für Satellitenassemblys optimiert.</span><span class="sxs-lookup"><span data-stu-id="cca5c-114">Specifies whether the common language runtime optimizes the probe for satellite assemblies.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="cca5c-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="cca5c-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="cca5c-116">value</span><span class="sxs-lookup"><span data-stu-id="cca5c-116">Value</span></span>|<span data-ttu-id="cca5c-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cca5c-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="cca5c-118">Die Laufzeit optimiert den Prüfpunkt für Satellitenassemblys nicht.</span><span class="sxs-lookup"><span data-stu-id="cca5c-118">The runtime does not optimize the probe for satellite assemblies.</span></span> <span data-ttu-id="cca5c-119">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="cca5c-119">This is the default value.</span></span>|  
|`true`|<span data-ttu-id="cca5c-120">Die Laufzeit optimiert die Sonde für Satellitenassemblys.</span><span class="sxs-lookup"><span data-stu-id="cca5c-120">The runtime optimizes the probe for satellite assemblies.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cca5c-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cca5c-121">Child Elements</span></span>  
 <span data-ttu-id="cca5c-122">Keine.</span><span class="sxs-lookup"><span data-stu-id="cca5c-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cca5c-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cca5c-123">Parent Elements</span></span>  
  
|<span data-ttu-id="cca5c-124">Element</span><span class="sxs-lookup"><span data-stu-id="cca5c-124">Element</span></span>|<span data-ttu-id="cca5c-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cca5c-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="cca5c-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="cca5c-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="cca5c-127">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="cca5c-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cca5c-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="cca5c-128">Remarks</span></span>  
 <span data-ttu-id="cca5c-129">Im Allgemeinen untersucht Resource Manager Ressourcen, wie im Thema [Verpackung und Bereitstellung von Ressourcen](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="cca5c-129">In general, Resource Manager probes for resources, as documented in the [Packaging and Deploying Resources](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md) topic.</span></span> <span data-ttu-id="cca5c-130">Dies bedeutet, dass Resource Manager, wenn er nach einer bestimmten lokalisierten Version einer Ressource sucht, im globalen Assemblycache suchen, in einem kulturspezifischen <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> Ordner in der Codebasis der Anwendung suchen, Windows Installer nach Satellitenassemblys abfragen und das Ereignis aushebe.</span><span class="sxs-lookup"><span data-stu-id="cca5c-130">This means that when Resource Manager probes for a particular localized version of a resource, it may look in the global assembly cache, look in a culture-specific folder in the application's code base, query Windows Installer for satellite assemblies, and raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="cca5c-131">Das `<relativeBindForResources>` Element optimiert die Art und Weise, in der Resource Manager für Satellitenassemblys untersucht wird.</span><span class="sxs-lookup"><span data-stu-id="cca5c-131">The `<relativeBindForResources>` element optimizes the way in which Resource Manager probes for satellite assemblies.</span></span> <span data-ttu-id="cca5c-132">Es kann die Leistung verbessern, wenn Ressourcen unter den folgenden Bedingungen gesucht werden:</span><span class="sxs-lookup"><span data-stu-id="cca5c-132">It can improve performance when probing for resources under the following conditions:</span></span>  
  
- <span data-ttu-id="cca5c-133">Wenn die Satellitenassembly am gleichen Speicherort wie die Codeassembly bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="cca5c-133">When the satellite assembly is deployed in the same location as the code assembly.</span></span> <span data-ttu-id="cca5c-134">Mit anderen Worten, wenn die Codeassembly im globalen Assemblycache installiert ist, müssen die Satellitenassemblys auch dort installiert werden.</span><span class="sxs-lookup"><span data-stu-id="cca5c-134">In other words, if the code assembly is installed in the global assembly cache, the satellite assemblies must also be installed there.</span></span> <span data-ttu-id="cca5c-135">Wenn die Codeassembly in der Codebasis der Anwendung installiert ist, müssen die Satellitenassemblys auch in einem kulturspezifischen Ordner in der Codebasis installiert werden.</span><span class="sxs-lookup"><span data-stu-id="cca5c-135">If the code assembly is installed in the application's code base, the satellite assemblies must also be installed in a culture-specific folder in the code base.</span></span>  
  
- <span data-ttu-id="cca5c-136">Wenn Windows Installer nicht oder nur selten für die Bedarfsinstallation von Satellitenassemblys verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cca5c-136">When Windows Installer is not used or is used only rarely for on-demand installation of satellite assemblies.</span></span>  
  
- <span data-ttu-id="cca5c-137">Wenn Anwendungscode das <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> Ereignis nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="cca5c-137">When application code does not handle the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="cca5c-138">Wenn `enabled` Sie das `<relativeBindForResources>` Attribut `true` des Elements so festlegen, dass der Resource Manager-Test für Satellitenassemblys wie folgt optimiert wird:</span><span class="sxs-lookup"><span data-stu-id="cca5c-138">Setting the `enabled` attribute of the `<relativeBindForResources>` element to `true` optimizes Resource Manager's probe for satellite assemblies as follows:</span></span>  
  
- <span data-ttu-id="cca5c-139">Es verwendet die Position der übergeordneten Codeassembly, um für die Satellitenassembly zu suchen.</span><span class="sxs-lookup"><span data-stu-id="cca5c-139">It uses the location of the parent code assembly to probe for the satellite assembly.</span></span>  
  
- <span data-ttu-id="cca5c-140">Windows Installer wird nicht nach Satellitenassemblys abgefragt.</span><span class="sxs-lookup"><span data-stu-id="cca5c-140">It does not query Windows Installer for satellite assemblies.</span></span>  
  
- <span data-ttu-id="cca5c-141">Es löst nicht <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> das Ereignis aus.</span><span class="sxs-lookup"><span data-stu-id="cca5c-141">It does not raise the <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cca5c-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cca5c-142">See also</span></span>

- [<span data-ttu-id="cca5c-143">Packaging and Deploying Resources</span><span class="sxs-lookup"><span data-stu-id="cca5c-143">Packaging and Deploying Resources</span></span>](../../../resources/packaging-and-deploying-resources-in-desktop-apps.md)
- [<span data-ttu-id="cca5c-144">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="cca5c-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="cca5c-145">Schema der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="cca5c-145">Configuration File Schema</span></span>](../index.md)
