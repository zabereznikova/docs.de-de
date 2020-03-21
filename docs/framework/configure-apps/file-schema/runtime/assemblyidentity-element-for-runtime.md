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
ms.openlocfilehash: b026dafbde796bbd8726de56b532ed6710ba2290
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154308"
---
# <a name="assemblyidentity-element-for-runtime"></a><span data-ttu-id="72bd2-102">\<assemblyIdentity> \<Element für Laufzeit></span><span class="sxs-lookup"><span data-stu-id="72bd2-102">\<assemblyIdentity> Element for \<runtime></span></span>
<span data-ttu-id="72bd2-103">Enthält identifizierende Informationen zur Assembly.</span><span class="sxs-lookup"><span data-stu-id="72bd2-103">Contains identifying information about the assembly.</span></span>  
  
<span data-ttu-id="72bd2-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="72bd2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="72bd2-105">&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="72bd2-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="72bd2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<AssemblyBinding>**](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="72bd2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="72bd2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)</span><span class="sxs-lookup"><span data-stu-id="72bd2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)</span></span>\
<span data-ttu-id="72bd2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyIdentität>**</span><span class="sxs-lookup"><span data-stu-id="72bd2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyIdentity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72bd2-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="72bd2-109">Syntax</span></span>  
  
```xml  
   <assemblyIdentity
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="72bd2-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="72bd2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="72bd2-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="72bd2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="72bd2-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="72bd2-112">Attributes</span></span>  
  
|<span data-ttu-id="72bd2-113">attribute</span><span class="sxs-lookup"><span data-stu-id="72bd2-113">Attribute</span></span>|<span data-ttu-id="72bd2-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72bd2-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="72bd2-115">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="72bd2-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="72bd2-116">Der Name der Assembly</span><span class="sxs-lookup"><span data-stu-id="72bd2-116">The name of the assembly</span></span>|  
|`culture`|<span data-ttu-id="72bd2-117">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="72bd2-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="72bd2-118">Eine Zeichenfolge, die die Sprache und das Land/die Region der Assembly angibt.</span><span class="sxs-lookup"><span data-stu-id="72bd2-118">A string that specifies the language and country/region of the assembly.</span></span>|  
|`publicKeyToken`|<span data-ttu-id="72bd2-119">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="72bd2-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="72bd2-120">Ein hexadezimaler Wert, der den starken Namen der Assembly angibt.</span><span class="sxs-lookup"><span data-stu-id="72bd2-120">A hexadecimal value that specifies the strong name of the assembly.</span></span>|  
|`processorArchitecture`|<span data-ttu-id="72bd2-121">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="72bd2-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="72bd2-122">Einer der Werte "x86", "amd64", "msil" oder "ia64", der die Prozessorarchitektur für eine Assembly angibt, die prozessorspezifischen Code enthält.</span><span class="sxs-lookup"><span data-stu-id="72bd2-122">One of the values "x86", "amd64", "msil", or "ia64", specifying the processor architecture for an assembly that contains processor-specific code.</span></span> <span data-ttu-id="72bd2-123">Bei den Werten wird die Groß-/Kleinschreibung nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="72bd2-123">The values are not case-sensitive.</span></span> <span data-ttu-id="72bd2-124">Wenn dem Attribut ein anderer Wert `<assemblyIdentity>` zugewiesen wird, wird das gesamte Element ignoriert.</span><span class="sxs-lookup"><span data-stu-id="72bd2-124">If the attribute is assigned any other value, the entire `<assemblyIdentity>` element is ignored.</span></span> <span data-ttu-id="72bd2-125">Siehe <xref:System.Reflection.ProcessorArchitecture>.</span><span class="sxs-lookup"><span data-stu-id="72bd2-125">See <xref:System.Reflection.ProcessorArchitecture>.</span></span>|  
  
## <a name="processorarchitecture-attribute"></a><span data-ttu-id="72bd2-126">processorArchitecture-Attribut</span><span class="sxs-lookup"><span data-stu-id="72bd2-126">processorArchitecture Attribute</span></span>  
  
|<span data-ttu-id="72bd2-127">value</span><span class="sxs-lookup"><span data-stu-id="72bd2-127">Value</span></span>|<span data-ttu-id="72bd2-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72bd2-128">Description</span></span>|  
|-----------|-----------------|  
|`amd64`|<span data-ttu-id="72bd2-129">Nur AMD x86-64-Architektur.</span><span class="sxs-lookup"><span data-stu-id="72bd2-129">AMD x86-64 architecture only.</span></span>|  
|`ia64`|<span data-ttu-id="72bd2-130">Nur Intel Itanium-Architektur.</span><span class="sxs-lookup"><span data-stu-id="72bd2-130">Intel Itanium architecture only.</span></span>|  
|`msil`|<span data-ttu-id="72bd2-131">Neutral hinsichtlich des Prozessors und der Bits pro Wort.</span><span class="sxs-lookup"><span data-stu-id="72bd2-131">Neutral with respect to processor and bits-per-word.</span></span>|  
|`x86`|<span data-ttu-id="72bd2-132">Ein 32-Bit-x86-Prozessor, entweder nativ oder in der Windows-unter Windows-Umgebung (WOW) auf einer 64-Bit-Plattform.</span><span class="sxs-lookup"><span data-stu-id="72bd2-132">A 32-bit x86 processor, either native or in the Windows on Windows (WOW) environment on a 64-bit platform.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="72bd2-133">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="72bd2-133">Child Elements</span></span>  
 <span data-ttu-id="72bd2-134">Keine.</span><span class="sxs-lookup"><span data-stu-id="72bd2-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="72bd2-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="72bd2-135">Parent Elements</span></span>  
  
|<span data-ttu-id="72bd2-136">Element</span><span class="sxs-lookup"><span data-stu-id="72bd2-136">Element</span></span>|<span data-ttu-id="72bd2-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72bd2-137">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="72bd2-138">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="72bd2-138">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="72bd2-139">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="72bd2-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="72bd2-140">Kapselt die Bindungsrichtlinie und den Assemblyspeicherort für jede Assembly.</span><span class="sxs-lookup"><span data-stu-id="72bd2-140">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="72bd2-141">Verwenden `<dependentAssembly>` Sie für jede Baugruppe ein Element.</span><span class="sxs-lookup"><span data-stu-id="72bd2-141">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="72bd2-142">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="72bd2-142">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72bd2-143">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="72bd2-143">Remarks</span></span>  
 <span data-ttu-id="72bd2-144">Jedes \*\* \<dependentAssembly>-Element\*\* muss über ein \*\* \<AssemblyIdentity->\*\* untergeordnetes Element verfügen.</span><span class="sxs-lookup"><span data-stu-id="72bd2-144">Every **\<dependentAssembly>** element must have one **\<assemblyIdentity>** child element.</span></span>  
  
 <span data-ttu-id="72bd2-145">Wenn `processorArchitecture` das Attribut vorhanden `<assemblyIdentity>` ist, gilt das Element nur für die Assembly mit der entsprechenden Prozessorarchitektur.</span><span class="sxs-lookup"><span data-stu-id="72bd2-145">If the `processorArchitecture` attribute is present, the `<assemblyIdentity>` element applies only to the assembly with the corresponding processor architecture.</span></span> <span data-ttu-id="72bd2-146">Wenn `processorArchitecture` das Attribut nicht `<assemblyIdentity>` vorhanden ist, kann das Element auf eine Assembly mit einer beliebigen Prozessorarchitektur angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="72bd2-146">If the `processorArchitecture` attribute is not present, the `<assemblyIdentity>` element can apply to an assembly with any processor architecture.</span></span>  
  
 <span data-ttu-id="72bd2-147">Das folgende Beispiel zeigt eine Konfigurationsdatei für zwei Assemblys mit demselben Namen, die auf zwei verschiedene Prozessorarchitekturen abzielen und deren Versionen nicht synchron verwaltet wurden. Wenn die Anwendung auf der x86-Plattform ausgeführt wird, gilt das erste `<assemblyIdentity>` Element, und das andere wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="72bd2-147">The following example shows a configuration file for two assemblies with the same name that target two different two processor architectures, and whose versions have not been maintained in synch. When the application executes on the x86 platform the first `<assemblyIdentity>` element applies and the other is ignored.</span></span> <span data-ttu-id="72bd2-148">Wenn die Anwendung auf einer anderen Plattform als x86 oder ia64 ausgeführt wird, werden beide ignoriert.</span><span class="sxs-lookup"><span data-stu-id="72bd2-148">If the application executes on a platform other than x86 or ia64, both are ignored.</span></span>  
  
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
  
 <span data-ttu-id="72bd2-149">Wenn eine Konfigurationsdatei `<assemblyIdentity>` ein `processorArchitecture` Element ohne Attribut enthält und kein Element enthält, `processorArchitecture` das mit der Plattform übereinstimmt, wird das Element ohne attribut verwendet.</span><span class="sxs-lookup"><span data-stu-id="72bd2-149">If a configuration file contains an `<assemblyIdentity>` element with no `processorArchitecture` attribute, and does not contain an element that matches the platform, the element without the `processorArchitecture` attribute is used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72bd2-150">Beispiel</span><span class="sxs-lookup"><span data-stu-id="72bd2-150">Example</span></span>  
 <span data-ttu-id="72bd2-151">Das folgende Beispiel zeigt, wie Informationen zu einer Assembly bereitstellen werden.</span><span class="sxs-lookup"><span data-stu-id="72bd2-151">The following example shows how to provide information about an assembly.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="72bd2-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="72bd2-152">See also</span></span>

- [<span data-ttu-id="72bd2-153">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="72bd2-153">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="72bd2-154">Schema der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="72bd2-154">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="72bd2-155">Umleiten von Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="72bd2-155">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
