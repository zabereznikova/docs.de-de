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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 581b19cf74dcb5c2d5c4a549847629503fe0b6ff
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252370"
---
# <a name="qualifyassembly-element"></a><span data-ttu-id="dbedd-102">\<qualifyAssembly-> Element</span><span class="sxs-lookup"><span data-stu-id="dbedd-102">\<qualifyAssembly> Element</span></span>
<span data-ttu-id="dbedd-103">Gibt den vollständigen Namen der Assembly an, die dynamisch geladen werden soll, wenn Sie ein Teilname verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="dbedd-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
<span data-ttu-id="dbedd-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dbedd-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dbedd-105">&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="dbedd-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="dbedd-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<assemblyBinding->** ](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="dbedd-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="dbedd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<qualifyAssembly>**</span><span class="sxs-lookup"><span data-stu-id="dbedd-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<qualifyAssembly>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbedd-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="dbedd-108">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dbedd-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dbedd-109">Attributes and Elements</span></span>  
 <span data-ttu-id="dbedd-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dbedd-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dbedd-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="dbedd-111">Attributes</span></span>  
  
|<span data-ttu-id="dbedd-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="dbedd-112">Attribute</span></span>|<span data-ttu-id="dbedd-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dbedd-113">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="dbedd-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="dbedd-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="dbedd-115">Gibt den partiellen Namen der Assembly an, wie Sie im Code angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="dbedd-115">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="dbedd-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="dbedd-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="dbedd-117">Gibt den vollständigen Namen der Assembly an, wie Sie im globalen Assemblycache angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="dbedd-117">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dbedd-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dbedd-118">Child Elements</span></span>  
 <span data-ttu-id="dbedd-119">Keine</span><span class="sxs-lookup"><span data-stu-id="dbedd-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dbedd-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dbedd-120">Parent Elements</span></span>  
  
|<span data-ttu-id="dbedd-121">Element</span><span class="sxs-lookup"><span data-stu-id="dbedd-121">Element</span></span>|<span data-ttu-id="dbedd-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dbedd-122">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="dbedd-123">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="dbedd-123">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="dbedd-124">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="dbedd-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="dbedd-125">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="dbedd-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dbedd-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dbedd-126">Remarks</span></span>  
 <span data-ttu-id="dbedd-127">Das Aufrufen <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> der-Methode mit partiellen Assemblynamen bewirkt, dass der Common Language Runtime nur im Anwendungs Basisverzeichnis nach der Assembly sucht.</span><span class="sxs-lookup"><span data-stu-id="dbedd-127">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="dbedd-128">Verwenden Sie das  **\<>-Element qualifyAssembly** in der Anwendungs Konfigurationsdatei, um die vollständigen Assemblyinformationen (Name, Version, öffentliches Schlüssel Token und Kultur) bereitzustellen, und bewirken Sie, dass die Common Language Runtime im globaler Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="dbedd-128">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="dbedd-129">Das **FullName** -Attribut muss die vier Felder der Assemblyidentität enthalten: Name, Version, öffentliches Schlüssel Token und Kultur.</span><span class="sxs-lookup"><span data-stu-id="dbedd-129">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="dbedd-130">Das **partialName** -Attribut muss teilweise auf eine Assembly verweisen.</span><span class="sxs-lookup"><span data-stu-id="dbedd-130">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="dbedd-131">Sie müssen mindestens den Textnamen der Assembly angeben (der häufigste Fall), Sie können jedoch auch Version, öffentliches Schlüssel Token oder Kultur (oder eine beliebige Kombination der vier, aber nicht alle vier) einschließen.</span><span class="sxs-lookup"><span data-stu-id="dbedd-131">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="dbedd-132">Der **partialName** muss mit dem in Ihrem-Befehl angegebenen Namen identisch sein.</span><span class="sxs-lookup"><span data-stu-id="dbedd-132">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="dbedd-133">Beispielsweise können Sie nicht als `"math"` **partialName** -Attribut in der Konfigurationsdatei angeben und im `Assembly.Load("math, Version=3.3.3.3")` Code aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="dbedd-133">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dbedd-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dbedd-134">Example</span></span>  
 <span data-ttu-id="dbedd-135">Im folgenden Beispiel wird der-Befehl `Assembly.Load("math")` logisch `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="dbedd-135">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dbedd-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dbedd-136">See also</span></span>

- [<span data-ttu-id="dbedd-137">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="dbedd-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="dbedd-138">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="dbedd-138">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- <span data-ttu-id="dbedd-139">[Teilassemblyverweise](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="dbedd-139">[Partial Assembly References](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span></span>
