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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153918"
---
# <a name="qualifyassembly-element"></a><span data-ttu-id="bc56b-102">\<qualifyAssembly>-Element</span><span class="sxs-lookup"><span data-stu-id="bc56b-102">\<qualifyAssembly> Element</span></span>
<span data-ttu-id="bc56b-103">Gibt den vollständigen Namen der Assembly an, die dynamisch geladen werden soll, wenn Sie ein Teilname verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bc56b-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<qualifyAssembly>**  
  
## <a name="syntax"></a><span data-ttu-id="bc56b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bc56b-104">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bc56b-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bc56b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="bc56b-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bc56b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bc56b-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="bc56b-107">Attributes</span></span>  
  
|<span data-ttu-id="bc56b-108">attribute</span><span class="sxs-lookup"><span data-stu-id="bc56b-108">Attribute</span></span>|<span data-ttu-id="bc56b-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bc56b-109">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="bc56b-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="bc56b-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="bc56b-111">Gibt den partiellen Namen der Assembly an, wie Sie im Code angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="bc56b-111">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="bc56b-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="bc56b-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="bc56b-113">Gibt den vollständigen Namen der Assembly an, wie Sie im globalen Assemblycache angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="bc56b-113">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bc56b-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bc56b-114">Child Elements</span></span>  
 <span data-ttu-id="bc56b-115">Keine</span><span class="sxs-lookup"><span data-stu-id="bc56b-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bc56b-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bc56b-116">Parent Elements</span></span>  
  
|<span data-ttu-id="bc56b-117">Element</span><span class="sxs-lookup"><span data-stu-id="bc56b-117">Element</span></span>|<span data-ttu-id="bc56b-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc56b-118">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="bc56b-119">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="bc56b-119">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="bc56b-120">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="bc56b-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="bc56b-121">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="bc56b-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc56b-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="bc56b-122">Remarks</span></span>  
 <span data-ttu-id="bc56b-123">Das Aufrufen der- <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> Methode mit partiellen Assemblynamen bewirkt, dass der Common Language Runtime nur im Anwendungs Basisverzeichnis nach der Assembly sucht.</span><span class="sxs-lookup"><span data-stu-id="bc56b-123">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="bc56b-124">Verwenden Sie das **\<qualifyAssembly>** -Element in der Anwendungs Konfigurationsdatei, um die vollständigen Assemblyinformationen (Name, Version, öffentliches Schlüssel Token und Kultur) bereitzustellen, und bewirken Sie, dass die Common Language Runtime im globalen Assemblycache nach der Assembly sucht.</span><span class="sxs-lookup"><span data-stu-id="bc56b-124">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="bc56b-125">Das **FullName** -Attribut muss die vier Felder der Assemblyidentität enthalten: Name, Version, öffentliches Schlüssel Token und Kultur.</span><span class="sxs-lookup"><span data-stu-id="bc56b-125">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="bc56b-126">Das **partialName** -Attribut muss teilweise auf eine Assembly verweisen.</span><span class="sxs-lookup"><span data-stu-id="bc56b-126">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="bc56b-127">Sie müssen mindestens den Textnamen der Assembly angeben (der häufigste Fall), Sie können jedoch auch Version, öffentliches Schlüssel Token oder Kultur (oder eine beliebige Kombination der vier, aber nicht alle vier) einschließen.</span><span class="sxs-lookup"><span data-stu-id="bc56b-127">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="bc56b-128">Der **partialName** muss mit dem in Ihrem-Befehl angegebenen Namen identisch sein.</span><span class="sxs-lookup"><span data-stu-id="bc56b-128">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="bc56b-129">Beispielsweise können Sie nicht `"math"` als **partialName** -Attribut in der Konfigurationsdatei angeben und `Assembly.Load("math, Version=3.3.3.3")` im Code aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="bc56b-129">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc56b-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc56b-130">Example</span></span>  
 <span data-ttu-id="bc56b-131">Im folgenden Beispiel wird der-Befehl logisch aufgerufen `Assembly.Load("math")` `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")` .</span><span class="sxs-lookup"><span data-stu-id="bc56b-131">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bc56b-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bc56b-132">See also</span></span>

- [<span data-ttu-id="bc56b-133">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="bc56b-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="bc56b-134">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="bc56b-134">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- <span data-ttu-id="bc56b-135">[Partielle Assemblyverweise](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="bc56b-135">[Partial Assembly References](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span></span>
