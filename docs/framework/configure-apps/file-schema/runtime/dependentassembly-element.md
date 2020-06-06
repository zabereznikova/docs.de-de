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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154204"
---
# <a name="dependentassembly-element"></a><span data-ttu-id="c9b21-102">\<dependentAssembly>-Element</span><span class="sxs-lookup"><span data-stu-id="c9b21-102">\<dependentAssembly> Element</span></span>
<span data-ttu-id="c9b21-103">Kapselt die Bindungsrichtlinie und den Assemblyspeicherort für jede Assembly.</span><span class="sxs-lookup"><span data-stu-id="c9b21-103">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="c9b21-104">Verwenden Sie ein- `dependentAssembly` Element für jede Assembly.</span><span class="sxs-lookup"><span data-stu-id="c9b21-104">Use one `dependentAssembly` element for each assembly.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dependentAssembly>**  
  
## <a name="syntax"></a><span data-ttu-id="c9b21-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c9b21-105">Syntax</span></span>  
  
```xml  
<dependentAssembly>
</dependentAssembly>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9b21-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c9b21-106">Attributes and Elements</span></span>  
 <span data-ttu-id="c9b21-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c9b21-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9b21-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="c9b21-108">Attributes</span></span>  
 <span data-ttu-id="c9b21-109">Keine</span><span class="sxs-lookup"><span data-stu-id="c9b21-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c9b21-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c9b21-110">Child Elements</span></span>  
  
|<span data-ttu-id="c9b21-111">Element</span><span class="sxs-lookup"><span data-stu-id="c9b21-111">Element</span></span>|<span data-ttu-id="c9b21-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c9b21-112">Description</span></span>|  
|-------------|-----------------|  
|`assemblyIdentity`|<span data-ttu-id="c9b21-113">Enthält identifizierende Informationen über die Assembly.</span><span class="sxs-lookup"><span data-stu-id="c9b21-113">Contains identifying information about the assembly.</span></span> <span data-ttu-id="c9b21-114">Dieses Element muss in jedem Element enthalten sein `dependentAssembly` .</span><span class="sxs-lookup"><span data-stu-id="c9b21-114">This element must be included in each `dependentAssembly` element.</span></span>|  
|`codeBase`|<span data-ttu-id="c9b21-115">Gibt an, wo die Runtime eine freigegebene Assembly finden kann, wenn Sie nicht auf dem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="c9b21-115">Specifies where the runtime can find a shared assembly if it is not installed on the computer.</span></span>|  
|`bindingRedirect`|<span data-ttu-id="c9b21-116">Leitet eine Assemblyversion in eine andere um.</span><span class="sxs-lookup"><span data-stu-id="c9b21-116">Redirects one assembly version to another.</span></span>|  
|`publisherPolicy`|<span data-ttu-id="c9b21-117">Gibt an, ob die Laufzeit die Herausgeber Richtlinie für diese Assembly anwendet.</span><span class="sxs-lookup"><span data-stu-id="c9b21-117">Specifies whether the runtime applies publisher policy for this assembly.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c9b21-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c9b21-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c9b21-119">Element</span><span class="sxs-lookup"><span data-stu-id="c9b21-119">Element</span></span>|<span data-ttu-id="c9b21-120">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c9b21-120">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="c9b21-121">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="c9b21-121">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="c9b21-122">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="c9b21-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c9b21-123">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c9b21-123">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c9b21-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c9b21-124">Example</span></span>  
 <span data-ttu-id="c9b21-125">Im folgenden Beispiel wird gezeigt, wie Sie Assemblyinformationen für zwei Assemblys Kapseln.</span><span class="sxs-lookup"><span data-stu-id="c9b21-125">The following example shows how to encapsulate assembly information for two assemblies.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c9b21-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c9b21-126">See also</span></span>

- [<span data-ttu-id="c9b21-127">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="c9b21-127">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c9b21-128">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="c9b21-128">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="c9b21-129">Umleiten von Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="c9b21-129">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
