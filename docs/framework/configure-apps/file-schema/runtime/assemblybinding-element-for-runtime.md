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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154321"
---
# <a name="assemblybinding-element-for-runtime"></a><span data-ttu-id="612a9-102">\<assemblyBinding>-Element für \<runtime></span><span class="sxs-lookup"><span data-stu-id="612a9-102">\<assemblyBinding> Element for \<runtime></span></span>
<span data-ttu-id="612a9-103">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="612a9-103">Contains information about assembly version redirection and the locations of assemblies.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="612a9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="612a9-104">Syntax</span></span>  
  
```xml  
      <assemblyBinding
   xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
</assemblyBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="612a9-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="612a9-105">Attributes and Elements</span></span>  
 <span data-ttu-id="612a9-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="612a9-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="612a9-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="612a9-107">Attributes</span></span>  
  
|<span data-ttu-id="612a9-108">attribute</span><span class="sxs-lookup"><span data-stu-id="612a9-108">Attribute</span></span>|<span data-ttu-id="612a9-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="612a9-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="612a9-110">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="612a9-110">**xmlns**</span></span>|<span data-ttu-id="612a9-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="612a9-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="612a9-112">Gibt den XML-Namespace an, der für die Assemblybindung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="612a9-112">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="612a9-113">Verwenden Sie die Zeichenfolge "urn:schemas-microsoft-com:asm.v1" als Wert.</span><span class="sxs-lookup"><span data-stu-id="612a9-113">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span>|  
|<span data-ttu-id="612a9-114">**AppliesTo**</span><span class="sxs-lookup"><span data-stu-id="612a9-114">**appliesTo**</span></span>|<span data-ttu-id="612a9-115">Gibt die Laufzeitversion an, die für die .NET Framework-Assemblyumleitungen gilt.</span><span class="sxs-lookup"><span data-stu-id="612a9-115">Specifies the runtime version the .NET Framework assembly redirection applies to.</span></span> <span data-ttu-id="612a9-116">Dieses optionale Attribut verwendet eine .NET Framework-Versionsnummer, um anzugeben, welche Version verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="612a9-116">This optional attribute uses a .NET Framework version number to indicate what version it applies to.</span></span> <span data-ttu-id="612a9-117">Wenn kein **appliesTo** -Attribut angegeben ist, **\<assemblyBinding>** gilt das-Element für alle Versionen der .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="612a9-117">If no **appliesTo** attribute is specified, the **\<assemblyBinding>** element applies to all versions of the .NET Framework.</span></span> <span data-ttu-id="612a9-118">Das **appliesTo** -Attribut wurde in .NET Framework Version 1,1; eingeführt. Sie wird von der .NET Framework Version 1,0 ignoriert.</span><span class="sxs-lookup"><span data-stu-id="612a9-118">The **appliesTo** attribute was introduced in .NET Framework version 1.1; it is ignored by the .NET Framework version 1.0.</span></span> <span data-ttu-id="612a9-119">Dies bedeutet, dass alle **\<assemblyBinding>** Elemente bei Verwendung der .NET Framework Version 1,0 angewendet werden, auch wenn ein **appliesTo** -Attribut angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="612a9-119">This means that all **\<assemblyBinding>** elements are applied when using the .NET Framework version 1.0, even if an **appliesTo** attribute is specified.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="612a9-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="612a9-120">Child Elements</span></span>  
  
|<span data-ttu-id="612a9-121">Element</span><span class="sxs-lookup"><span data-stu-id="612a9-121">Element</span></span>|<span data-ttu-id="612a9-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="612a9-122">Description</span></span>|  
|-------------|-----------------|  
|[\<dependentAssembly>](dependentassembly-element.md)|<span data-ttu-id="612a9-123">Kapselt die Bindungsrichtlinie und den Assemblyspeicherort für eine Assembly.</span><span class="sxs-lookup"><span data-stu-id="612a9-123">Encapsulates binding policy and assembly location for an assembly.</span></span> <span data-ttu-id="612a9-124">Verwenden Sie **\<dependentAssembly>** für jede Assembly ein Tag.</span><span class="sxs-lookup"><span data-stu-id="612a9-124">Use one **\<dependentAssembly>** tag for each assembly.</span></span>|  
|[\<probing>](probing-element.md)|<span data-ttu-id="612a9-125">Gibt Unterverzeichnisse an, die die Common Language Runtime beim Laden von Assemblys durchsucht.</span><span class="sxs-lookup"><span data-stu-id="612a9-125">Specifies subdirectories the common language runtime searches when loading assemblies.</span></span>|  
|[\<publisherPolicy>](publisherpolicy-element.md)|<span data-ttu-id="612a9-126">Gibt an, ob die Common Language Runtime die Herausgeberrichtlinie anwendet.</span><span class="sxs-lookup"><span data-stu-id="612a9-126">Specifies whether the runtime applies publisher policy.</span></span>|  
|[\<qualifyAssembly>](qualifyassembly-element.md)|<span data-ttu-id="612a9-127">Gibt den vollständigen Namen der Assembly an, die dynamisch geladen werden soll, wenn Sie ein Teilname verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="612a9-127">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="612a9-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="612a9-128">Parent Elements</span></span>  
  
|<span data-ttu-id="612a9-129">Element</span><span class="sxs-lookup"><span data-stu-id="612a9-129">Element</span></span>|<span data-ttu-id="612a9-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="612a9-130">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="612a9-131">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="612a9-131">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="612a9-132">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="612a9-132">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="612a9-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="612a9-133">Example</span></span>  
 <span data-ttu-id="612a9-134">Das folgende Beispiel veranschaulicht, wie Sie eine Assemblyversion zu einer anderen umleiten und eine Codebasis bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="612a9-134">The following example shows how to redirect one assembly version to another and provide a codebase.</span></span>  
  
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
  
 <span data-ttu-id="612a9-135">Im folgenden Beispiel wird gezeigt, wie das **appliesTo** -Attribut verwendet wird, um die Bindung einer .NET Framework Assembly umzuleiten.</span><span class="sxs-lookup"><span data-stu-id="612a9-135">The following example shows how to use the **appliesTo** attribute to redirect binding of a .NET Framework assembly.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="612a9-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="612a9-136">See also</span></span>

- [<span data-ttu-id="612a9-137">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="612a9-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="612a9-138">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="612a9-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="612a9-139">Umleiten von Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="612a9-139">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
