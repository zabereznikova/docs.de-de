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
ms.openlocfilehash: 26b265996a059d8e52901557603bcf5e7636e596
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195219"
---
# <a name="qualifyassembly-element"></a><span data-ttu-id="07288-102">\<qualifyAssembly>-Element</span><span class="sxs-lookup"><span data-stu-id="07288-102">\<qualifyAssembly> Element</span></span>

<span data-ttu-id="07288-103">Gibt den vollständigen Namen der Assembly an, die dynamisch geladen werden soll, wenn Sie ein Teilname verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="07288-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<qualifyAssembly>**  
  
## <a name="syntax"></a><span data-ttu-id="07288-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="07288-104">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07288-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="07288-105">Attributes and Elements</span></span>  

 <span data-ttu-id="07288-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="07288-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07288-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="07288-107">Attributes</span></span>  
  
|<span data-ttu-id="07288-108">attribute</span><span class="sxs-lookup"><span data-stu-id="07288-108">Attribute</span></span>|<span data-ttu-id="07288-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07288-109">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="07288-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="07288-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="07288-111">Gibt den partiellen Namen der Assembly an, wie Sie im Code angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="07288-111">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="07288-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="07288-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="07288-113">Gibt den vollständigen Namen der Assembly an, wie Sie im globalen Assemblycache angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="07288-113">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="07288-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="07288-114">Child Elements</span></span>  

 <span data-ttu-id="07288-115">Keine</span><span class="sxs-lookup"><span data-stu-id="07288-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="07288-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="07288-116">Parent Elements</span></span>  
  
|<span data-ttu-id="07288-117">Element</span><span class="sxs-lookup"><span data-stu-id="07288-117">Element</span></span>|<span data-ttu-id="07288-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07288-118">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="07288-119">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="07288-119">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="07288-120">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="07288-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="07288-121">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="07288-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07288-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="07288-122">Remarks</span></span>  

 <span data-ttu-id="07288-123">Das Aufrufen der- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> Methode mit partiellen Assemblynamen bewirkt, dass der Common Language Runtime nur im Anwendungs Basisverzeichnis nach der Assembly sucht.</span><span class="sxs-lookup"><span data-stu-id="07288-123">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="07288-124">Verwenden Sie das **\<qualifyAssembly>** -Element in der Anwendungs Konfigurationsdatei, um die vollständigen Assemblyinformationen (Name, Version, öffentliches Schlüssel Token und Kultur) bereitzustellen, und bewirken Sie, dass die Common Language Runtime im globalen Assemblycache nach der Assembly sucht.</span><span class="sxs-lookup"><span data-stu-id="07288-124">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="07288-125">Das **FullName** -Attribut muss die vier Felder der Assemblyidentität enthalten: Name, Version, öffentliches Schlüssel Token und Kultur.</span><span class="sxs-lookup"><span data-stu-id="07288-125">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="07288-126">Das **partialName** -Attribut muss teilweise auf eine Assembly verweisen.</span><span class="sxs-lookup"><span data-stu-id="07288-126">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="07288-127">Sie müssen mindestens den Textnamen der Assembly angeben (der häufigste Fall), Sie können jedoch auch Version, öffentliches Schlüssel Token oder Kultur (oder eine beliebige Kombination der vier, aber nicht alle vier) einschließen.</span><span class="sxs-lookup"><span data-stu-id="07288-127">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="07288-128">Der **partialName** muss mit dem in Ihrem-Befehl angegebenen Namen identisch sein.</span><span class="sxs-lookup"><span data-stu-id="07288-128">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="07288-129">Beispielsweise können Sie nicht `"math"` als **partialName** -Attribut in der Konfigurationsdatei angeben und `Assembly.Load("math, Version=3.3.3.3")` im Code aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="07288-129">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07288-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07288-130">Example</span></span>  

 <span data-ttu-id="07288-131">Im folgenden Beispiel wird der-Befehl logisch aufgerufen `Assembly.Load("math")` `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")` .</span><span class="sxs-lookup"><span data-stu-id="07288-131">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="07288-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="07288-132">See also</span></span>

- [<span data-ttu-id="07288-133">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="07288-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="07288-134">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="07288-134">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- <span data-ttu-id="07288-135">[Partielle Assemblyverweise](/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="07288-135">[Partial Assembly References](/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span></span>
