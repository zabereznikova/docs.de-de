---
title: <assemblyBinding>-Element für <runtime>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding
helpviewer_keywords:
- <assemblyBinding> element
- assemblyBinding element
- container tags, <assemblyBinding> element
ms.assetid: 964cbb35-ab49-4498-8471-209689e5dada
ms.openlocfilehash: 202b063ad3f0f9696cdc12aff434d61fe5a813e6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154321"
---
# <a name="assemblybinding-element-for-runtime"></a><span data-ttu-id="1ed82-102">\<assemblyBinding> \<Element für Laufzeit></span><span class="sxs-lookup"><span data-stu-id="1ed82-102">\<assemblyBinding> Element for \<runtime></span></span>
<span data-ttu-id="1ed82-103">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="1ed82-103">Contains information about assembly version redirection and the locations of assemblies.</span></span>  
  
<span data-ttu-id="1ed82-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1ed82-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1ed82-105">&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="1ed82-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="1ed82-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<AssemblyBinding>**</span><span class="sxs-lookup"><span data-stu-id="1ed82-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ed82-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ed82-107">Syntax</span></span>  
  
```xml  
      <assemblyBinding
   xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
</assemblyBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ed82-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1ed82-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1ed82-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1ed82-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ed82-110">Attributes</span><span class="sxs-lookup"><span data-stu-id="1ed82-110">Attributes</span></span>  
  
|<span data-ttu-id="1ed82-111">attribute</span><span class="sxs-lookup"><span data-stu-id="1ed82-111">Attribute</span></span>|<span data-ttu-id="1ed82-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ed82-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1ed82-113">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="1ed82-113">**xmlns**</span></span>|<span data-ttu-id="1ed82-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="1ed82-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="1ed82-115">Gibt den XML-Namespace an, der für die Assemblybindung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1ed82-115">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="1ed82-116">Verwenden Sie die Zeichenfolge "urn:schemas-microsoft-com:asm.v1" als Wert.</span><span class="sxs-lookup"><span data-stu-id="1ed82-116">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span>|  
|<span data-ttu-id="1ed82-117">**Appliesto**</span><span class="sxs-lookup"><span data-stu-id="1ed82-117">**appliesTo**</span></span>|<span data-ttu-id="1ed82-118">Gibt die Laufzeitversion an, die für die .NET Framework-Assemblyumleitungen gilt.</span><span class="sxs-lookup"><span data-stu-id="1ed82-118">Specifies the runtime version the .NET Framework assembly redirection applies to.</span></span> <span data-ttu-id="1ed82-119">Dieses optionale Attribut verwendet eine .NET Framework-Versionsnummer, um anzugeben, welche Version verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1ed82-119">This optional attribute uses a .NET Framework version number to indicate what version it applies to.</span></span> <span data-ttu-id="1ed82-120">Ohne Angabe eines **appliesTo**-Attributs gilt das **\<assemblyBinding>**-Element für alle Versionen von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1ed82-120">If no **appliesTo** attribute is specified, the **\<assemblyBinding>** element applies to all versions of the .NET Framework.</span></span> <span data-ttu-id="1ed82-121">Das **attribut appliesTo** wurde in .NET Framework Version 1.1 eingeführt. es wird von der .NET Framework Version 1.0 ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1ed82-121">The **appliesTo** attribute was introduced in .NET Framework version 1.1; it is ignored by the .NET Framework version 1.0.</span></span> <span data-ttu-id="1ed82-122">Dies bedeutet, dass alle \*\* \<AssemblyBinding->-Elemente\*\* angewendet werden, wenn .NET Framework Version 1.0 verwendet wird, auch wenn ein **appliesTo-Attribut** angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="1ed82-122">This means that all **\<assemblyBinding>** elements are applied when using the .NET Framework version 1.0, even if an **appliesTo** attribute is specified.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1ed82-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1ed82-123">Child Elements</span></span>  
  
|<span data-ttu-id="1ed82-124">Element</span><span class="sxs-lookup"><span data-stu-id="1ed82-124">Element</span></span>|<span data-ttu-id="1ed82-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ed82-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ed82-126">\<dependentAssembly></span><span class="sxs-lookup"><span data-stu-id="1ed82-126">\<dependentAssembly></span></span>](dependentassembly-element.md)|<span data-ttu-id="1ed82-127">Kapselt die Bindungsrichtlinie und den Assemblyspeicherort für eine Assembly.</span><span class="sxs-lookup"><span data-stu-id="1ed82-127">Encapsulates binding policy and assembly location for an assembly.</span></span> <span data-ttu-id="1ed82-128">Verwenden Sie für jede Assembly ein \*\* \<abhängiges Assembly->-Tag.\*\*</span><span class="sxs-lookup"><span data-stu-id="1ed82-128">Use one **\<dependentAssembly>** tag for each assembly.</span></span>|  
|[<span data-ttu-id="1ed82-129">\<Prüfen></span><span class="sxs-lookup"><span data-stu-id="1ed82-129">\<probing></span></span>](probing-element.md)|<span data-ttu-id="1ed82-130">Gibt Unterverzeichnisse an, die die Common Language Runtime beim Laden von Assemblys durchsucht.</span><span class="sxs-lookup"><span data-stu-id="1ed82-130">Specifies subdirectories the common language runtime searches when loading assemblies.</span></span>|  
|[<span data-ttu-id="1ed82-131">\<publisherPolicy></span><span class="sxs-lookup"><span data-stu-id="1ed82-131">\<publisherPolicy></span></span>](publisherpolicy-element.md)|<span data-ttu-id="1ed82-132">Gibt an, ob die Common Language Runtime die Herausgeberrichtlinie anwendet.</span><span class="sxs-lookup"><span data-stu-id="1ed82-132">Specifies whether the runtime applies publisher policy.</span></span>|  
|[<span data-ttu-id="1ed82-133">\<qualifyAssembly></span><span class="sxs-lookup"><span data-stu-id="1ed82-133">\<qualifyAssembly></span></span>](qualifyassembly-element.md)|<span data-ttu-id="1ed82-134">Gibt den vollständigen Namen der Assembly an, die dynamisch geladen werden soll, wenn Sie ein Teilname verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1ed82-134">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1ed82-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1ed82-135">Parent Elements</span></span>  
  
|<span data-ttu-id="1ed82-136">Element</span><span class="sxs-lookup"><span data-stu-id="1ed82-136">Element</span></span>|<span data-ttu-id="1ed82-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1ed82-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1ed82-138">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="1ed82-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="1ed82-139">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1ed82-139">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1ed82-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ed82-140">Example</span></span>  
 <span data-ttu-id="1ed82-141">Das folgende Beispiel veranschaulicht, wie Sie eine Assemblyversion zu einer anderen umleiten und eine Codebasis bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1ed82-141">The following example shows how to redirect one assembly version to another and provide a codebase.</span></span>  
  
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
  
 <span data-ttu-id="1ed82-142">Das folgende Beispiel zeigt, wie das **attribute appliesTo** verwendet wird, um die Bindung einer .NET Framework-Assembly umzuleiten.</span><span class="sxs-lookup"><span data-stu-id="1ed82-142">The following example shows how to use the **appliesTo** attribute to redirect binding of a .NET Framework assembly.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1ed82-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ed82-143">See also</span></span>

- [<span data-ttu-id="1ed82-144">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="1ed82-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="1ed82-145">Schema der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="1ed82-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="1ed82-146">Umleiten von Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="1ed82-146">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
