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
ms.openlocfilehash: 6a4741c6a4745bdba00fdb525b39b70d0b15e005
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59109447"
---
# <a name="qualifyassembly-element"></a><span data-ttu-id="89e01-102">\<QualifyAssembly >-Element</span><span class="sxs-lookup"><span data-stu-id="89e01-102">\<qualifyAssembly> Element</span></span>
<span data-ttu-id="89e01-103">Gibt den vollständigen Namen der Assembly an, die dynamisch geladen werden soll, wenn Sie ein Teilname verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="89e01-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
 <span data-ttu-id="89e01-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="89e01-104">\<configuration></span></span>  
<span data-ttu-id="89e01-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="89e01-105">\<runtime></span></span>  
<span data-ttu-id="89e01-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="89e01-106">\<assemblyBinding></span></span>  
<span data-ttu-id="89e01-107">\<qualifyAssembly></span><span class="sxs-lookup"><span data-stu-id="89e01-107">\<qualifyAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89e01-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="89e01-108">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89e01-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="89e01-109">Attributes and Elements</span></span>  
 <span data-ttu-id="89e01-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="89e01-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89e01-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="89e01-111">Attributes</span></span>  
  
|<span data-ttu-id="89e01-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="89e01-112">Attribute</span></span>|<span data-ttu-id="89e01-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89e01-113">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="89e01-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="89e01-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="89e01-115">Gibt den Teil des Namens der Assembly an, wie er im Code angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="89e01-115">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="89e01-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="89e01-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="89e01-117">Gibt den vollständigen Namen der Assembly an, wie er im globalen Assemblycache angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="89e01-117">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="89e01-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="89e01-118">Child Elements</span></span>  
 <span data-ttu-id="89e01-119">Keine</span><span class="sxs-lookup"><span data-stu-id="89e01-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="89e01-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="89e01-120">Parent Elements</span></span>  
  
|<span data-ttu-id="89e01-121">Element</span><span class="sxs-lookup"><span data-stu-id="89e01-121">Element</span></span>|<span data-ttu-id="89e01-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89e01-122">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="89e01-123">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="89e01-123">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="89e01-124">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="89e01-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="89e01-125">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="89e01-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89e01-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="89e01-126">Remarks</span></span>  
 <span data-ttu-id="89e01-127">Aufrufen der <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> mit partiellen Assemblynamen Methode bewirkt, dass die common Language Runtime die Assembly nur im Basisverzeichnis Anwendung gesucht.</span><span class="sxs-lookup"><span data-stu-id="89e01-127">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="89e01-128">Verwenden der  **\<QualifyAssembly >** Element in der Konfigurationsdatei der Anwendung geben Sie die vollständige Assemblyinformationen (Name, Version, öffentliches Schlüsseltoken und Kultur) und dazu führen, dass die common Language Runtime suchen für die Assembly im globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="89e01-128">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="89e01-129">Die **"FullName"** Attribut muss vier Felder der Assemblyidentität enthalten: Name, Version, Kultur und Token des öffentlichen Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="89e01-129">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="89e01-130">Die **PartialName** Attribut muss teilweise auf eine Assembly verweisen.</span><span class="sxs-lookup"><span data-stu-id="89e01-130">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="89e01-131">Geben Sie mindestens den Namen der Assembly Text (die am häufigsten verwendeten Fall), aber Sie können auch die Version, Token des öffentlichen Schlüssels oder Kultur (oder eine beliebige Kombination aus den vier, aber nicht alle vier) einschließen.</span><span class="sxs-lookup"><span data-stu-id="89e01-131">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="89e01-132">Die **PartialName** muss den im Aufruf angegebenen Namen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="89e01-132">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="89e01-133">Angenommen, Sie können nicht angeben, `"math"` als die **PartialName** Attribut in Ihrer Konfigurationsdatei, und rufen `Assembly.Load("math, Version=3.3.3.3")` in Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="89e01-133">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="89e01-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89e01-134">Example</span></span>  
 <span data-ttu-id="89e01-135">Im folgende Beispiel wird logisch der Aufruf `Assembly.Load("math")` in `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span><span class="sxs-lookup"><span data-stu-id="89e01-135">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="89e01-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89e01-136">See also</span></span>

- [<span data-ttu-id="89e01-137">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="89e01-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="89e01-138">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="89e01-138">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- <span data-ttu-id="89e01-139">[Partielle Assemblyverweise](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="89e01-139">[Partial Assembly References](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span></span>
