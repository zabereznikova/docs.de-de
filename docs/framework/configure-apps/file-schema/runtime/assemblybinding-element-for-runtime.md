---
title: '&lt;AssemblyBinding&gt; -Element für &lt;Common Language Runtime&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding
helpviewer_keywords:
- <assemblyBinding> element
- assemblyBinding element
- container tags, <assemblyBinding> element
ms.assetid: 964cbb35-ab49-4498-8471-209689e5dada
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 33900f40aab85fd67540ecd6004a46e13e8eb8c2
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612035"
---
# <a name="ltassemblybindinggt-element-for-ltruntimegt"></a><span data-ttu-id="03a5f-102">&lt;AssemblyBinding&gt; -Element für &lt;Common Language Runtime&gt;</span><span class="sxs-lookup"><span data-stu-id="03a5f-102">&lt;assemblyBinding&gt; Element for &lt;runtime&gt;</span></span>
<span data-ttu-id="03a5f-103">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="03a5f-103">Contains information about assembly version redirection and the locations of assemblies.</span></span>  
  
 <span data-ttu-id="03a5f-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="03a5f-104">\<configuration></span></span>  
<span data-ttu-id="03a5f-105">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="03a5f-105">\<runtime></span></span>  
<span data-ttu-id="03a5f-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="03a5f-106">\<assemblyBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03a5f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="03a5f-107">Syntax</span></span>  
  
```xml  
      <assemblyBinding    
   xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
</assemblyBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03a5f-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="03a5f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="03a5f-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="03a5f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03a5f-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="03a5f-110">Attributes</span></span>  
  
|<span data-ttu-id="03a5f-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="03a5f-111">Attribute</span></span>|<span data-ttu-id="03a5f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="03a5f-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="03a5f-113">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="03a5f-113">**xmlns**</span></span>|<span data-ttu-id="03a5f-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="03a5f-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="03a5f-115">Gibt den XML-Namespace an, der für die Assemblybindung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="03a5f-115">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="03a5f-116">Verwenden Sie die Zeichenfolge "urn:schemas-microsoft-com:asm.v1" als Wert.</span><span class="sxs-lookup"><span data-stu-id="03a5f-116">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span>|  
|<span data-ttu-id="03a5f-117">**AppliesTo**</span><span class="sxs-lookup"><span data-stu-id="03a5f-117">**appliesTo**</span></span>|<span data-ttu-id="03a5f-118">Gibt die Laufzeitversion an, die für die .NET Framework-Assemblyumleitungen gilt.</span><span class="sxs-lookup"><span data-stu-id="03a5f-118">Specifies the runtime version the .NET Framework assembly redirection applies to.</span></span> <span data-ttu-id="03a5f-119">Dieses optionale Attribut verwendet eine .NET Framework-Versionsnummer, um anzugeben, welche Version verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="03a5f-119">This optional attribute uses a .NET Framework version number to indicate what version it applies to.</span></span> <span data-ttu-id="03a5f-120">Ohne Angabe eines **appliesTo**-Attributs gilt das **\<assemblyBinding>**-Element für alle Versionen von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="03a5f-120">If no **appliesTo** attribute is specified, the **\<assemblyBinding>** element applies to all versions of the .NET Framework.</span></span> <span data-ttu-id="03a5f-121">Die **AppliesTo** Attribut wurde in .NET Framework, Version 1.1 eingeführt; es wird von .NET Framework, Version 1.0 ignoriert.</span><span class="sxs-lookup"><span data-stu-id="03a5f-121">The **appliesTo** attribute was introduced in .NET Framework version 1.1; it is ignored by the .NET Framework version 1.0.</span></span> <span data-ttu-id="03a5f-122">Dies bedeutet, dass alle **\<assemblyBinding>**-Elemente bei Verwendung von .NET Framework Version 1.0 angewendet werden, auch wenn das **appliesTo**-Attribut angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="03a5f-122">This means that all **\<assemblyBinding>** elements are applied when using the .NET Framework version 1.0, even if an **appliesTo** attribute is specified.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="03a5f-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="03a5f-123">Child Elements</span></span>  
  
|<span data-ttu-id="03a5f-124">Element</span><span class="sxs-lookup"><span data-stu-id="03a5f-124">Element</span></span>|<span data-ttu-id="03a5f-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="03a5f-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="03a5f-126">\<dependentAssembly></span><span class="sxs-lookup"><span data-stu-id="03a5f-126">\<dependentAssembly></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/dependentassembly-element.md)|<span data-ttu-id="03a5f-127">Kapselt die Bindungsrichtlinie und den Assemblyspeicherort für eine Assembly.</span><span class="sxs-lookup"><span data-stu-id="03a5f-127">Encapsulates binding policy and assembly location for an assembly.</span></span> <span data-ttu-id="03a5f-128">Verwenden Sie eine  **\<DependentAssembly >** Tag für jede Assembly.</span><span class="sxs-lookup"><span data-stu-id="03a5f-128">Use one **\<dependentAssembly>** tag for each assembly.</span></span>|  
|[<span data-ttu-id="03a5f-129">\<probing></span><span class="sxs-lookup"><span data-stu-id="03a5f-129">\<probing></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)|<span data-ttu-id="03a5f-130">Gibt Unterverzeichnisse an, die die Common Language Runtime beim Laden von Assemblys durchsucht.</span><span class="sxs-lookup"><span data-stu-id="03a5f-130">Specifies subdirectories the common language runtime searches when loading assemblies.</span></span>|  
|[<span data-ttu-id="03a5f-131">\<publisherPolicy></span><span class="sxs-lookup"><span data-stu-id="03a5f-131">\<publisherPolicy></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md)|<span data-ttu-id="03a5f-132">Gibt an, ob die Common Language Runtime die Herausgeberrichtlinie anwendet.</span><span class="sxs-lookup"><span data-stu-id="03a5f-132">Specifies whether the runtime applies publisher policy.</span></span>|  
|[<span data-ttu-id="03a5f-133">\<qualifyAssembly></span><span class="sxs-lookup"><span data-stu-id="03a5f-133">\<qualifyAssembly></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/qualifyassembly-element.md)|<span data-ttu-id="03a5f-134">Gibt den vollständigen Namen der Assembly an, die dynamisch geladen werden soll, wenn Sie ein Teilname verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="03a5f-134">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="03a5f-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="03a5f-135">Parent Elements</span></span>  
  
|<span data-ttu-id="03a5f-136">Element</span><span class="sxs-lookup"><span data-stu-id="03a5f-136">Element</span></span>|<span data-ttu-id="03a5f-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="03a5f-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="03a5f-138">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="03a5f-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="03a5f-139">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="03a5f-139">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="03a5f-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="03a5f-140">Example</span></span>  
 <span data-ttu-id="03a5f-141">Das folgende Beispiel veranschaulicht, wie Sie eine Assemblyversion zu einer anderen umleiten und eine Codebasis bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="03a5f-141">The following example shows how to redirect one assembly version to another and provide a codebase.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="03a5f-142">Das folgende Beispiel zeigt, wie Sie mit der **AppliesTo** Attribut zum Umleiten der Bindung einer .NET Framework-Assembly.</span><span class="sxs-lookup"><span data-stu-id="03a5f-142">The following example shows how to use the **appliesTo** attribute to redirect binding of a .NET Framework assembly.</span></span>  
  
```xml  
<runtime>  
   <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
      <dependentAssembly>   
         <assemblyIdentity name="mscorcfg" publicKeyToken="b03f5f7f11d50a3a" culture=""/>  
         <bindingRedirect oldVersion="0.0.0.0-65535.65535.65535.65535" newVersion="1.0.3300.0"/>  
      </dependentAssembly>  
   </assemblyBinding>  
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="03a5f-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03a5f-143">See Also</span></span>  
- [<span data-ttu-id="03a5f-144">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="03a5f-144">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
- [<span data-ttu-id="03a5f-145">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="03a5f-145">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
- [<span data-ttu-id="03a5f-146">Umleiten von Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="03a5f-146">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
