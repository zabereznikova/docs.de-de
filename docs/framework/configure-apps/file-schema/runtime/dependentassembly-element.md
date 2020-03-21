---
title: <dependentAssembly>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#dependentAssembly
helpviewer_keywords:
- container tags, <dependentAssembly> element
- dependentAssembly element
- <dependentAssembly> element
ms.assetid: 14e95627-dd79-4b82-ac85-e682aa3a31d8
ms.openlocfilehash: 2de8c752867d00708173d11d1851f415a2e8518d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154204"
---
# <a name="dependentassembly-element"></a><span data-ttu-id="e47c9-102">\<dependentAssembly> Element</span><span class="sxs-lookup"><span data-stu-id="e47c9-102">\<dependentAssembly> Element</span></span>
<span data-ttu-id="e47c9-103">Kapselt die Bindungsrichtlinie und den Assemblyspeicherort für jede Assembly.</span><span class="sxs-lookup"><span data-stu-id="e47c9-103">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="e47c9-104">Verwenden `dependentAssembly` Sie für jede Baugruppe ein Element.</span><span class="sxs-lookup"><span data-stu-id="e47c9-104">Use one `dependentAssembly` element for each assembly.</span></span>  
  
<span data-ttu-id="e47c9-105">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e47c9-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e47c9-106">&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="e47c9-106">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="e47c9-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<AssemblyBinding>**](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="e47c9-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="e47c9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dependentAssembly>**</span><span class="sxs-lookup"><span data-stu-id="e47c9-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dependentAssembly>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e47c9-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="e47c9-109">Syntax</span></span>  
  
```xml  
<dependentAssembly>
</dependentAssembly>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e47c9-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e47c9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e47c9-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e47c9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e47c9-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="e47c9-112">Attributes</span></span>  
 <span data-ttu-id="e47c9-113">Keine.</span><span class="sxs-lookup"><span data-stu-id="e47c9-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e47c9-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e47c9-114">Child Elements</span></span>  
  
|<span data-ttu-id="e47c9-115">Element</span><span class="sxs-lookup"><span data-stu-id="e47c9-115">Element</span></span>|<span data-ttu-id="e47c9-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e47c9-116">Description</span></span>|  
|-------------|-----------------|  
|`assemblyIdentity`|<span data-ttu-id="e47c9-117">Enthält identifizierende Informationen zur Assembly.</span><span class="sxs-lookup"><span data-stu-id="e47c9-117">Contains identifying information about the assembly.</span></span> <span data-ttu-id="e47c9-118">Dieses Element muss in `dependentAssembly` jedem Element enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="e47c9-118">This element must be included in each `dependentAssembly` element.</span></span>|  
|`codeBase`|<span data-ttu-id="e47c9-119">Gibt an, wo die Laufzeit eine freigegebene Assembly finden kann, wenn sie nicht auf dem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="e47c9-119">Specifies where the runtime can find a shared assembly if it is not installed on the computer.</span></span>|  
|`bindingRedirect`|<span data-ttu-id="e47c9-120">Leitet eine Assemblyversion in eine andere um.</span><span class="sxs-lookup"><span data-stu-id="e47c9-120">Redirects one assembly version to another.</span></span>|  
|`publisherPolicy`|<span data-ttu-id="e47c9-121">Gibt an, ob die Laufzeit Die Herausgeberrichtlinie für diese Assembly anwendet.</span><span class="sxs-lookup"><span data-stu-id="e47c9-121">Specifies whether the runtime applies publisher policy for this assembly.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e47c9-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e47c9-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e47c9-123">Element</span><span class="sxs-lookup"><span data-stu-id="e47c9-123">Element</span></span>|<span data-ttu-id="e47c9-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e47c9-124">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="e47c9-125">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="e47c9-125">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="e47c9-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e47c9-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e47c9-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="e47c9-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e47c9-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e47c9-128">Example</span></span>  
 <span data-ttu-id="e47c9-129">Das folgende Beispiel zeigt, wie Baugruppeninformationen für zwei Baugruppen gekapselt werden.</span><span class="sxs-lookup"><span data-stu-id="e47c9-129">The following example shows how to encapsulate assembly information for two assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="mySecondAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for mySecondAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e47c9-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e47c9-130">See also</span></span>

- [<span data-ttu-id="e47c9-131">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="e47c9-131">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e47c9-132">Schema der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="e47c9-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e47c9-133">Umleiten von Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="e47c9-133">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
