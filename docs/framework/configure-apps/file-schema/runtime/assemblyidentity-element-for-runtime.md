---
title: <assemblyIdentity>-Element für <runtime>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity
helpviewer_keywords:
- <assemblyIdentity> element
- container tags, <assemblyIdentity> element
- assemblyIdentity element
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
ms.openlocfilehash: f3e74b05ac0fd7c57963f2aad047ba3f2d63a10a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91170180"
---
# <a name="assemblyidentity-element-for-runtime"></a><span data-ttu-id="bfef8-102">\<assemblyIdentity>-Element für \<runtime></span><span class="sxs-lookup"><span data-stu-id="bfef8-102">\<assemblyIdentity> Element for \<runtime></span></span>

<span data-ttu-id="bfef8-103">Enthält identifizierende Informationen über die Assembly.</span><span class="sxs-lookup"><span data-stu-id="bfef8-103">Contains identifying information about the assembly.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyIdentity>**  
  
## <a name="syntax"></a><span data-ttu-id="bfef8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bfef8-104">Syntax</span></span>  
  
```xml  
   <assemblyIdentity
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bfef8-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bfef8-105">Attributes and Elements</span></span>  

 <span data-ttu-id="bfef8-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bfef8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bfef8-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="bfef8-107">Attributes</span></span>  
  
|<span data-ttu-id="bfef8-108">attribute</span><span class="sxs-lookup"><span data-stu-id="bfef8-108">Attribute</span></span>|<span data-ttu-id="bfef8-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bfef8-109">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="bfef8-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="bfef8-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="bfef8-111">Der Name der Assembly.</span><span class="sxs-lookup"><span data-stu-id="bfef8-111">The name of the assembly</span></span>|  
|`culture`|<span data-ttu-id="bfef8-112">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="bfef8-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="bfef8-113">Eine Zeichenfolge, die die Sprache und das Land/die Region der Assembly angibt.</span><span class="sxs-lookup"><span data-stu-id="bfef8-113">A string that specifies the language and country/region of the assembly.</span></span>|  
|`publicKeyToken`|<span data-ttu-id="bfef8-114">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="bfef8-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="bfef8-115">Ein Hexadezimalwert, der den starken Namen der Assembly angibt.</span><span class="sxs-lookup"><span data-stu-id="bfef8-115">A hexadecimal value that specifies the strong name of the assembly.</span></span>|  
|`processorArchitecture`|<span data-ttu-id="bfef8-116">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="bfef8-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="bfef8-117">Einer der Werte "x86", "amd64", "MSIL" oder "ia64", der die Prozessorarchitektur für eine Assembly angibt, die Prozessor spezifischen Code enthält.</span><span class="sxs-lookup"><span data-stu-id="bfef8-117">One of the values "x86", "amd64", "msil", or "ia64", specifying the processor architecture for an assembly that contains processor-specific code.</span></span> <span data-ttu-id="bfef8-118">Bei Werten wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="bfef8-118">The values are not case-sensitive.</span></span> <span data-ttu-id="bfef8-119">Wenn dem Attribut ein beliebiger anderer Wert zugewiesen wird, `<assemblyIdentity>` wird das gesamte Element ignoriert.</span><span class="sxs-lookup"><span data-stu-id="bfef8-119">If the attribute is assigned any other value, the entire `<assemblyIdentity>` element is ignored.</span></span> <span data-ttu-id="bfef8-120">Siehe <xref:System.Reflection.ProcessorArchitecture>.</span><span class="sxs-lookup"><span data-stu-id="bfef8-120">See <xref:System.Reflection.ProcessorArchitecture>.</span></span>|  
  
## <a name="processorarchitecture-attribute"></a><span data-ttu-id="bfef8-121">ProcessorArchitecture-Attribut</span><span class="sxs-lookup"><span data-stu-id="bfef8-121">processorArchitecture Attribute</span></span>  
  
|<span data-ttu-id="bfef8-122">Wert</span><span class="sxs-lookup"><span data-stu-id="bfef8-122">Value</span></span>|<span data-ttu-id="bfef8-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bfef8-123">Description</span></span>|  
|-----------|-----------------|  
|`amd64`|<span data-ttu-id="bfef8-124">Nur AMD x86-64-Architektur.</span><span class="sxs-lookup"><span data-stu-id="bfef8-124">AMD x86-64 architecture only.</span></span>|  
|`ia64`|<span data-ttu-id="bfef8-125">Nur Intel Itanium-Architektur.</span><span class="sxs-lookup"><span data-stu-id="bfef8-125">Intel Itanium architecture only.</span></span>|  
|`msil`|<span data-ttu-id="bfef8-126">Neutral hinsichtlich des Prozessors und der Bits pro Wort.</span><span class="sxs-lookup"><span data-stu-id="bfef8-126">Neutral with respect to processor and bits-per-word.</span></span>|  
|`x86`|<span data-ttu-id="bfef8-127">Ein 32-Bit-x86-Prozessor, entweder System eigen oder in der WOW-Umgebung (Windows on Windows) auf einer 64-Bit-Plattform.</span><span class="sxs-lookup"><span data-stu-id="bfef8-127">A 32-bit x86 processor, either native or in the Windows on Windows (WOW) environment on a 64-bit platform.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bfef8-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bfef8-128">Child Elements</span></span>  

 <span data-ttu-id="bfef8-129">Keine</span><span class="sxs-lookup"><span data-stu-id="bfef8-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bfef8-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bfef8-130">Parent Elements</span></span>  
  
|<span data-ttu-id="bfef8-131">Element</span><span class="sxs-lookup"><span data-stu-id="bfef8-131">Element</span></span>|<span data-ttu-id="bfef8-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bfef8-132">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="bfef8-133">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="bfef8-133">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="bfef8-134">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="bfef8-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="bfef8-135">Kapselt die Bindungsrichtlinie und den Assemblyspeicherort für jede Assembly.</span><span class="sxs-lookup"><span data-stu-id="bfef8-135">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="bfef8-136">Verwenden Sie ein- `<dependentAssembly>` Element für jede Assembly.</span><span class="sxs-lookup"><span data-stu-id="bfef8-136">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="bfef8-137">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="bfef8-137">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bfef8-138">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="bfef8-138">Remarks</span></span>  

 <span data-ttu-id="bfef8-139">Jedes **\<dependentAssembly>** Element muss über ein untergeordnetes **\<assemblyIdentity>** Element verfügen.</span><span class="sxs-lookup"><span data-stu-id="bfef8-139">Every **\<dependentAssembly>** element must have one **\<assemblyIdentity>** child element.</span></span>  
  
 <span data-ttu-id="bfef8-140">Wenn das- `processorArchitecture` Attribut vorhanden ist, `<assemblyIdentity>` gilt das-Element nur für die Assembly mit der entsprechenden Prozessorarchitektur.</span><span class="sxs-lookup"><span data-stu-id="bfef8-140">If the `processorArchitecture` attribute is present, the `<assemblyIdentity>` element applies only to the assembly with the corresponding processor architecture.</span></span> <span data-ttu-id="bfef8-141">Wenn das- `processorArchitecture` Attribut nicht vorhanden ist, `<assemblyIdentity>` kann das-Element auf eine Assembly mit beliebiger Prozessorarchitektur angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="bfef8-141">If the `processorArchitecture` attribute is not present, the `<assemblyIdentity>` element can apply to an assembly with any processor architecture.</span></span>  
  
 <span data-ttu-id="bfef8-142">Das folgende Beispiel zeigt eine Konfigurationsdatei für zwei Assemblys mit dem gleichen Namen, die zwei unterschiedliche zwei Prozessorarchitekturen als Ziel haben und deren Versionen nicht synchron aufbewahrt wurden. Wenn die Anwendung auf der x86-Plattform ausgeführt wird, wird das erste `<assemblyIdentity>` Element angewendet, und das andere wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="bfef8-142">The following example shows a configuration file for two assemblies with the same name that target two different two processor architectures, and whose versions have not been maintained in synch. When the application executes on the x86 platform the first `<assemblyIdentity>` element applies and the other is ignored.</span></span> <span data-ttu-id="bfef8-143">Wenn die Anwendung auf einer anderen Plattform als x86 oder ia64 ausgeführt wird, werden beide ignoriert.</span><span class="sxs-lookup"><span data-stu-id="bfef8-143">If the application executes on a platform other than x86 or ia64, both are ignored.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"  
                  processorArchitecture="x86" />  
            <bindingRedirect oldVersion= "1.0.0.0"
                  newVersion="1.1.0.0" />  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"
                  processorArchitecture="ia64" />  
            <bindingRedirect oldVersion="1.0.0.0"
                  newVersion="2.0.0.0" />  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="bfef8-144">Wenn eine Konfigurationsdatei ein `<assemblyIdentity>` Element `processorArchitecture` ohne Attribut enthält und kein Element enthält, das mit der Plattform übereinstimmt, wird das-Element ohne das- `processorArchitecture` Attribut verwendet.</span><span class="sxs-lookup"><span data-stu-id="bfef8-144">If a configuration file contains an `<assemblyIdentity>` element with no `processorArchitecture` attribute, and does not contain an element that matches the platform, the element without the `processorArchitecture` attribute is used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bfef8-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bfef8-145">Example</span></span>  

 <span data-ttu-id="bfef8-146">Im folgenden Beispiel wird gezeigt, wie Informationen zu einer Assembly bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="bfef8-146">The following example shows how to provide information about an assembly.</span></span>  
  
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
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bfef8-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bfef8-147">See also</span></span>

- [<span data-ttu-id="bfef8-148">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="bfef8-148">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="bfef8-149">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="bfef8-149">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="bfef8-150">Umleiten von Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="bfef8-150">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
