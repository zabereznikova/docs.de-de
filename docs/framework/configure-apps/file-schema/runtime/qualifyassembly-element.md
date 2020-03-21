---
title: <qualifyAssembly>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly
helpviewer_keywords:
- container tags, <qualifyAssembly> element
- <qualifyAssembly> element
- qualifyAssembly element
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
ms.openlocfilehash: 74e83900c68ab4b3fe01beb3f97657b0140d78ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153918"
---
# <a name="qualifyassembly-element"></a><span data-ttu-id="c1489-102">\<qualifyAssembly> Element</span><span class="sxs-lookup"><span data-stu-id="c1489-102">\<qualifyAssembly> Element</span></span>
<span data-ttu-id="c1489-103">Gibt den vollständigen Namen der Assembly an, die dynamisch geladen werden soll, wenn Sie ein Teilname verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c1489-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
<span data-ttu-id="c1489-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c1489-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c1489-105">&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="c1489-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="c1489-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<AssemblyBinding>**](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="c1489-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="c1489-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<qualifyAssembly>**</span><span class="sxs-lookup"><span data-stu-id="c1489-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<qualifyAssembly>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1489-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1489-108">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1489-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c1489-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c1489-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c1489-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1489-111">Attributes</span><span class="sxs-lookup"><span data-stu-id="c1489-111">Attributes</span></span>  
  
|<span data-ttu-id="c1489-112">attribute</span><span class="sxs-lookup"><span data-stu-id="c1489-112">Attribute</span></span>|<span data-ttu-id="c1489-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1489-113">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="c1489-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="c1489-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="c1489-115">Gibt den Teilnamen der Assembly an, wie er im Code angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c1489-115">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="c1489-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="c1489-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="c1489-117">Gibt den vollständigen Namen der Assembly an, wie er im globalen Assemblycache angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c1489-117">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c1489-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1489-118">Child Elements</span></span>  
 <span data-ttu-id="c1489-119">Keine.</span><span class="sxs-lookup"><span data-stu-id="c1489-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c1489-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1489-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c1489-121">Element</span><span class="sxs-lookup"><span data-stu-id="c1489-121">Element</span></span>|<span data-ttu-id="c1489-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1489-122">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="c1489-123">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="c1489-123">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="c1489-124">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="c1489-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c1489-125">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="c1489-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1489-126">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c1489-126">Remarks</span></span>  
 <span data-ttu-id="c1489-127">Wenn <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> Sie die Methode mithilfe partieller Assemblynamen aufrufen, wird die Common Language Runtime nur im Anwendungsbasisverzeichnis nach der Assembly suchen.</span><span class="sxs-lookup"><span data-stu-id="c1489-127">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="c1489-128">Verwenden Sie das \*\* \<qualifyAssembly>-Element\*\* in der Anwendungskonfigurationsdatei, um die vollständigen Assemblyinformationen (Name, Version, öffentliches Schlüsseltoken und Kultur) bereitzustellen und die Common Language-Laufzeit im globalen Assemblycache nach der Assembly zu suchen.</span><span class="sxs-lookup"><span data-stu-id="c1489-128">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="c1489-129">Das **fullName-Attribut** muss die vier Felder der Assemblyidentität enthalten: Name, Version, öffentliches Schlüsseltoken und Kultur.</span><span class="sxs-lookup"><span data-stu-id="c1489-129">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="c1489-130">Das **partialName-Attribut** muss teilweise auf eine Assembly verweisen.</span><span class="sxs-lookup"><span data-stu-id="c1489-130">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="c1489-131">Sie müssen mindestens den Textnamen der Assembly angeben (der häufigste Fall), aber Sie können auch Version, öffentliches Schlüsseltoken oder Kultur (oder eine beliebige Kombination der vier, aber nicht alle vier) einschließen.</span><span class="sxs-lookup"><span data-stu-id="c1489-131">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="c1489-132">Der **partialName** muss mit dem in Ihrem Aufruf angegebenen Namen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="c1489-132">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="c1489-133">Sie können z. `"math"` B. nicht als **partielles Name-Attribut** in Ihrer Konfigurationsdatei und als Aufruf `Assembly.Load("math, Version=3.3.3.3")` im Code angeben.</span><span class="sxs-lookup"><span data-stu-id="c1489-133">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1489-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c1489-134">Example</span></span>  
 <span data-ttu-id="c1489-135">Im folgenden Beispiel wird `Assembly.Load("math")` der `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`Aufruf logisch in .</span><span class="sxs-lookup"><span data-stu-id="c1489-135">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c1489-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c1489-136">See also</span></span>

- [<span data-ttu-id="c1489-137">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="c1489-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c1489-138">So sucht die Laufzeit Assemblys</span><span class="sxs-lookup"><span data-stu-id="c1489-138">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- <span data-ttu-id="c1489-139">[Partielle Assemblyverweise](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c1489-139">[Partial Assembly References](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span></span>
