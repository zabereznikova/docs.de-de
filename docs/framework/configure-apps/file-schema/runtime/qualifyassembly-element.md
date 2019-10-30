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
ms.openlocfilehash: 17cfe9fc39d65f146beef5d02c701f5e3e2fbbe1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115782"
---
# <a name="qualifyassembly-element"></a><span data-ttu-id="57f0c-102">\<qualifyAssembly > Element</span><span class="sxs-lookup"><span data-stu-id="57f0c-102">\<qualifyAssembly> Element</span></span>
<span data-ttu-id="57f0c-103">Gibt den vollständigen Namen der Assembly an, die dynamisch geladen werden soll, wenn Sie ein Teilname verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="57f0c-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
<span data-ttu-id="57f0c-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="57f0c-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="57f0c-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="57f0c-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="57f0c-106">&nbsp; &nbsp; &nbsp; &nbsp;[ **\<assemblyBinding**](assemblybinding-element-for-runtime.md) > </span><span class="sxs-lookup"><span data-stu-id="57f0c-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="57f0c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<qualifyAssembly >**</span><span class="sxs-lookup"><span data-stu-id="57f0c-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<qualifyAssembly>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57f0c-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="57f0c-108">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="57f0c-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="57f0c-109">Attributes and Elements</span></span>  
 <span data-ttu-id="57f0c-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="57f0c-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="57f0c-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="57f0c-111">Attributes</span></span>  
  
|<span data-ttu-id="57f0c-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="57f0c-112">Attribute</span></span>|<span data-ttu-id="57f0c-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="57f0c-113">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="57f0c-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="57f0c-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="57f0c-115">Gibt den partiellen Namen der Assembly an, wie Sie im Code angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="57f0c-115">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="57f0c-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="57f0c-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="57f0c-117">Gibt den vollständigen Namen der Assembly an, wie Sie im globalen Assemblycache angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="57f0c-117">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="57f0c-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="57f0c-118">Child Elements</span></span>  
 <span data-ttu-id="57f0c-119">Keine</span><span class="sxs-lookup"><span data-stu-id="57f0c-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="57f0c-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="57f0c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="57f0c-121">Element</span><span class="sxs-lookup"><span data-stu-id="57f0c-121">Element</span></span>|<span data-ttu-id="57f0c-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="57f0c-122">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="57f0c-123">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="57f0c-123">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="57f0c-124">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="57f0c-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="57f0c-125">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="57f0c-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57f0c-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="57f0c-126">Remarks</span></span>  
 <span data-ttu-id="57f0c-127">Wenn Sie die <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>-Methode mit partiellen Assemblynamen aufrufen, werden die Common Language Runtime nur im Anwendungs Basisverzeichnis nach der Assembly gesucht.</span><span class="sxs-lookup"><span data-stu-id="57f0c-127">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="57f0c-128">Verwenden Sie das **\<qualifyAssembly->** Element in der Anwendungs Konfigurationsdatei, um die vollständigen Assemblyinformationen (Name, Version, öffentliches Schlüssel Token und Kultur) bereitzustellen, und bewirken Sie, dass die Common Language Runtime in der globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="57f0c-128">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="57f0c-129">Das **FullName** -Attribut muss die vier Felder der Assemblyidentität enthalten: Name, Version, öffentliches Schlüssel Token und Kultur.</span><span class="sxs-lookup"><span data-stu-id="57f0c-129">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="57f0c-130">Das **partialName** -Attribut muss teilweise auf eine Assembly verweisen.</span><span class="sxs-lookup"><span data-stu-id="57f0c-130">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="57f0c-131">Sie müssen mindestens den Textnamen der Assembly angeben (der häufigste Fall), Sie können jedoch auch Version, öffentliches Schlüssel Token oder Kultur (oder eine beliebige Kombination der vier, aber nicht alle vier) einschließen.</span><span class="sxs-lookup"><span data-stu-id="57f0c-131">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="57f0c-132">Der **partialName** muss mit dem in Ihrem-Befehl angegebenen Namen identisch sein.</span><span class="sxs-lookup"><span data-stu-id="57f0c-132">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="57f0c-133">Beispielsweise können Sie `"math"` nicht als **partialName** -Attribut in der Konfigurationsdatei angeben und `Assembly.Load("math, Version=3.3.3.3")` im Code aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="57f0c-133">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57f0c-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="57f0c-134">Example</span></span>  
 <span data-ttu-id="57f0c-135">Im folgenden Beispiel wird der `Assembly.Load("math")` des Aufrufes logisch in `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="57f0c-135">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="57f0c-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57f0c-136">See also</span></span>

- [<span data-ttu-id="57f0c-137">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="57f0c-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="57f0c-138">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="57f0c-138">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- <span data-ttu-id="57f0c-139">[Teilassemblyverweise](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="57f0c-139">[Partial Assembly References](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span></span>
