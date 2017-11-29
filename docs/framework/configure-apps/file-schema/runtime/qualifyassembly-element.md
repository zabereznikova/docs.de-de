---
title: '&lt;QualifyAssembly&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly
helpviewer_keywords:
- container tags, <qualifyAssembly> element
- <qualifyAssembly> element
- qualifyAssembly element
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 521bbccd83f224cc824dae41309715d65472454e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltqualifyassemblygt-element"></a><span data-ttu-id="af88a-102">&lt;QualifyAssembly&gt; Element</span><span class="sxs-lookup"><span data-stu-id="af88a-102">&lt;qualifyAssembly&gt; Element</span></span>
<span data-ttu-id="af88a-103">Gibt den vollständigen Namen der Assembly an, die dynamisch geladen werden soll, wenn Sie ein Teilname verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="af88a-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
 <span data-ttu-id="af88a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="af88a-104">\<configuration></span></span>  
<span data-ttu-id="af88a-105">\<Common Language Runtime ></span><span class="sxs-lookup"><span data-stu-id="af88a-105">\<runtime></span></span>  
<span data-ttu-id="af88a-106">\<AssemblyBinding ></span><span class="sxs-lookup"><span data-stu-id="af88a-106">\<assemblyBinding></span></span>  
<span data-ttu-id="af88a-107">\<QualifyAssembly ></span><span class="sxs-lookup"><span data-stu-id="af88a-107">\<qualifyAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af88a-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="af88a-108">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af88a-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="af88a-109">Attributes and Elements</span></span>  
 <span data-ttu-id="af88a-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="af88a-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af88a-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="af88a-111">Attributes</span></span>  
  
|<span data-ttu-id="af88a-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="af88a-112">Attribute</span></span>|<span data-ttu-id="af88a-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af88a-113">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="af88a-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="af88a-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="af88a-115">Gibt die partielle Name der Assembly an, wie er im Code angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="af88a-115">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="af88a-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="af88a-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="af88a-117">Gibt den vollständigen Namen der Assembly an, wie er im globalen Assemblycache angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="af88a-117">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af88a-118">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="af88a-118">Child Elements</span></span>  
 <span data-ttu-id="af88a-119">Keine</span><span class="sxs-lookup"><span data-stu-id="af88a-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="af88a-120">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="af88a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="af88a-121">Element</span><span class="sxs-lookup"><span data-stu-id="af88a-121">Element</span></span>|<span data-ttu-id="af88a-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af88a-122">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="af88a-123">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="af88a-123">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="af88a-124">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="af88a-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="af88a-125">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="af88a-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af88a-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="af88a-126">Remarks</span></span>  
 <span data-ttu-id="af88a-127">Aufrufen der <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> mit partiellen Assemblynamen Methode bewirkt, dass die common Language Runtime für die Assembly nur im Basisverzeichnis Anwendung gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="af88a-127">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="af88a-128">Verwenden der  **\<QualifyAssembly >** Element in der Konfigurationsdatei der Anwendung geben Sie die vollständige Assemblyinformationen (Name, Version, öffentliches Schlüsseltoken und Kultur) und dazu führen, dass die common Language Runtime, gesucht werden soll für die Assembly im globalen Assemblycache.</span><span class="sxs-lookup"><span data-stu-id="af88a-128">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="af88a-129">Die **FullName** Attribut muss vier Felder der Assemblyidentität enthalten: Name, Version, öffentliches Schlüsseltoken und Kultur.</span><span class="sxs-lookup"><span data-stu-id="af88a-129">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="af88a-130">Die **PartialName** Attribut muss teilweise auf eine Assembly verweisen.</span><span class="sxs-lookup"><span data-stu-id="af88a-130">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="af88a-131">Geben Sie mindestens den Namen der Assembly Text (die am häufigsten vorkommen), aber Sie können auch die Version, Token des öffentlichen Schlüssels oder Kultur (oder eine beliebige Kombination aus den vier, aber nicht alle vier) einschließen.</span><span class="sxs-lookup"><span data-stu-id="af88a-131">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="af88a-132">Die **PartialName** muss die im Aufruf angegebenen Namen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="af88a-132">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="af88a-133">Angenommen, Sie können nicht angeben, `"math"` als die **PartialName** Attribut in der Konfigurationsdatei und der Aufruf `Assembly.Load("math, Version=3.3.3.3")` im Code.</span><span class="sxs-lookup"><span data-stu-id="af88a-133">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af88a-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="af88a-134">Example</span></span>  
 <span data-ttu-id="af88a-135">Im folgende Beispiel wird logisch der Aufruf `Assembly.Load("math")` in `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span><span class="sxs-lookup"><span data-stu-id="af88a-135">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="af88a-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af88a-136">See Also</span></span>  
 [<span data-ttu-id="af88a-137">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="af88a-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="af88a-138">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="af88a-138">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="af88a-139">NIB: Partielle Assemblyverweise</span><span class="sxs-lookup"><span data-stu-id="af88a-139">NIB: Partial Assembly References</span></span>](http://msdn.microsoft.com/en-us/ec90f07a-398c-4306-9401-0fc5ff9cb59f)
