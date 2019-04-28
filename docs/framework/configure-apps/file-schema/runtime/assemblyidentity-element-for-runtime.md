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
ms.openlocfilehash: d5766b76f18dce441cb260887a753dcf64642a6f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674232"
---
# <a name="assemblyidentity-element-for-runtime"></a><span data-ttu-id="93a8e-102">\<AssemblyIdentity >-Element für \<Runtime ></span><span class="sxs-lookup"><span data-stu-id="93a8e-102">\<assemblyIdentity> Element for \<runtime></span></span>
<span data-ttu-id="93a8e-103">Enthält identifizierende Informationen für die Assembly an.</span><span class="sxs-lookup"><span data-stu-id="93a8e-103">Contains identifying information about the assembly.</span></span>  
  
 <span data-ttu-id="93a8e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="93a8e-104">\<configuration></span></span>  
<span data-ttu-id="93a8e-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="93a8e-105">\<runtime></span></span>  
<span data-ttu-id="93a8e-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="93a8e-106">\<assemblyBinding></span></span>  
<span data-ttu-id="93a8e-107">\<dependentAssembly></span><span class="sxs-lookup"><span data-stu-id="93a8e-107">\<dependentAssembly></span></span>  
<span data-ttu-id="93a8e-108">\<assemblyIdentity></span><span class="sxs-lookup"><span data-stu-id="93a8e-108">\<assemblyIdentity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93a8e-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="93a8e-109">Syntax</span></span>  
  
```xml  
   <assemblyIdentity    
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="93a8e-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="93a8e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="93a8e-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="93a8e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="93a8e-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="93a8e-112">Attributes</span></span>  
  
|<span data-ttu-id="93a8e-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="93a8e-113">Attribute</span></span>|<span data-ttu-id="93a8e-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="93a8e-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="93a8e-115">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="93a8e-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="93a8e-116">Der Name der assembly</span><span class="sxs-lookup"><span data-stu-id="93a8e-116">The name of the assembly</span></span>|  
|`culture`|<span data-ttu-id="93a8e-117">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="93a8e-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="93a8e-118">Eine Zeichenfolge, die Sprache und Land/Region der Assembly angibt.</span><span class="sxs-lookup"><span data-stu-id="93a8e-118">A string that specifies the language and country/region of the assembly.</span></span>|  
|`publicKeyToken`|<span data-ttu-id="93a8e-119">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="93a8e-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="93a8e-120">Ein Hexadezimalwert, der den starken Namen der Assembly angibt.</span><span class="sxs-lookup"><span data-stu-id="93a8e-120">A hexadecimal value that specifies the strong name of the assembly.</span></span>|  
|`processorArchitecture`|<span data-ttu-id="93a8e-121">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="93a8e-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="93a8e-122">Eines der Werte "X86", "amd64", "Msil" oder "ia64" Angeben von der Prozessorarchitektur für eine Assembly, die Prozessor-spezifischen Code enthält.</span><span class="sxs-lookup"><span data-stu-id="93a8e-122">One of the values "x86", "amd64", "msil", or "ia64", specifying the processor architecture for an assembly that contains processor-specific code.</span></span> <span data-ttu-id="93a8e-123">Die Werte sind keine Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="93a8e-123">The values are not case-sensitive.</span></span> <span data-ttu-id="93a8e-124">Wenn das Attribut auf einen anderen Wert, den gesamten zugewiesen ist `<assemblyIdentity>` Element wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="93a8e-124">If the attribute is assigned any other value, the entire `<assemblyIdentity>` element is ignored.</span></span> <span data-ttu-id="93a8e-125">Siehe <xref:System.Reflection.ProcessorArchitecture>.</span><span class="sxs-lookup"><span data-stu-id="93a8e-125">See <xref:System.Reflection.ProcessorArchitecture>.</span></span>|  
  
## <a name="processorarchitecture-attribute"></a><span data-ttu-id="93a8e-126">ProcessorArchitecture-Attribut</span><span class="sxs-lookup"><span data-stu-id="93a8e-126">processorArchitecture Attribute</span></span>  
  
|<span data-ttu-id="93a8e-127">Wert</span><span class="sxs-lookup"><span data-stu-id="93a8e-127">Value</span></span>|<span data-ttu-id="93a8e-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="93a8e-128">Description</span></span>|  
|-----------|-----------------|  
|`amd64`|<span data-ttu-id="93a8e-129">Nur AMD X86-64-Architektur.</span><span class="sxs-lookup"><span data-stu-id="93a8e-129">AMD x86-64 architecture only.</span></span>|  
|`ia64`|<span data-ttu-id="93a8e-130">Nur Intel Itanium-Architektur.</span><span class="sxs-lookup"><span data-stu-id="93a8e-130">Intel Itanium architecture only.</span></span>|  
|`msil`|<span data-ttu-id="93a8e-131">Neutral hinsichtlich des Prozessors und die Bits pro Wort.</span><span class="sxs-lookup"><span data-stu-id="93a8e-131">Neutral with respect to processor and bits-per-word.</span></span>|  
|`x86`|<span data-ttu-id="93a8e-132">Eine 32-Bit-X86 Prozessor, entweder systemeigen oder in der Windows auf Windows (WOW)-Umgebung auf einer 64-Bit-Plattform.</span><span class="sxs-lookup"><span data-stu-id="93a8e-132">A 32-bit x86 processor, either native or in the Windows on Windows (WOW) environment on a 64-bit platform.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="93a8e-133">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="93a8e-133">Child Elements</span></span>  
 <span data-ttu-id="93a8e-134">Keine</span><span class="sxs-lookup"><span data-stu-id="93a8e-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="93a8e-135">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="93a8e-135">Parent Elements</span></span>  
  
|<span data-ttu-id="93a8e-136">Element</span><span class="sxs-lookup"><span data-stu-id="93a8e-136">Element</span></span>|<span data-ttu-id="93a8e-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="93a8e-137">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="93a8e-138">Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.</span><span class="sxs-lookup"><span data-stu-id="93a8e-138">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="93a8e-139">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="93a8e-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="93a8e-140">Kapselt die Bindungsrichtlinie und den Assemblyspeicherort für jede Assembly.</span><span class="sxs-lookup"><span data-stu-id="93a8e-140">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="93a8e-141">Verwenden Sie eine `<dependentAssembly>` -Element für jede Assembly.</span><span class="sxs-lookup"><span data-stu-id="93a8e-141">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="93a8e-142">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="93a8e-142">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="93a8e-143">Hinweise</span><span class="sxs-lookup"><span data-stu-id="93a8e-143">Remarks</span></span>  
 <span data-ttu-id="93a8e-144">Jede  **\<DependentAssembly >** Element benötigen einen  **\<AssemblyIdentity >** untergeordnetes Element.</span><span class="sxs-lookup"><span data-stu-id="93a8e-144">Every **\<dependentAssembly>** element must have one **\<assemblyIdentity>** child element.</span></span>  
  
 <span data-ttu-id="93a8e-145">Wenn die `processorArchitecture` -Attribut vorhanden ist, die `<assemblyIdentity>` Element gilt nur für die Assembly mit der entsprechenden Prozessorarchitektur.</span><span class="sxs-lookup"><span data-stu-id="93a8e-145">If the `processorArchitecture` attribute is present, the `<assemblyIdentity>` element applies only to the assembly with the corresponding processor architecture.</span></span> <span data-ttu-id="93a8e-146">Wenn die `processorArchitecture` Attribut ist nicht vorhanden, die `<assemblyIdentity>` Element auf eine Assembly mit einer beliebigen Prozessorarchitektur anwenden kann.</span><span class="sxs-lookup"><span data-stu-id="93a8e-146">If the `processorArchitecture` attribute is not present, the `<assemblyIdentity>` element can apply to an assembly with any processor architecture.</span></span>  
  
 <span data-ttu-id="93a8e-147">Das folgende Beispiel zeigt eine Konfigurationsdatei für zwei Assemblys mit demselben Namen, die zwei verschiedene Prozessorarchitekturen in zwei vorgesehen und, deren Versionen müssen nicht synchron beibehalten wurde. Wenn die Anwendung ausgeführt wird, auf die X86 Plattform die erste `<assemblyIdentity>` Element angewendet wird und der andere Wert wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="93a8e-147">The following example shows a configuration file for two assemblies with the same name that target two different two processor architectures, and whose versions have not been maintained in synch. When the application executes on the x86 platform the first `<assemblyIdentity>` element applies and the other is ignored.</span></span> <span data-ttu-id="93a8e-148">Wenn die Anwendung auf einer anderen Plattform als X86 oder ia64 ausgeführt wird, werden beide ignoriert.</span><span class="sxs-lookup"><span data-stu-id="93a8e-148">If the application executes on a platform other than x86 or ia64, both are ignored.</span></span>  
  
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
  
 <span data-ttu-id="93a8e-149">Wenn eine Konfigurationsdatei enthält eine `<assemblyIdentity>` Element ohne `processorArchitecture` Attribut, und enthält ein Element, das der Plattform, die dem Element ohne entspricht nicht der `processorArchitecture` Attribut wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="93a8e-149">If a configuration file contains an `<assemblyIdentity>` element with no `processorArchitecture` attribute, and does not contain an element that matches the platform, the element without the `processorArchitecture` attribute is used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93a8e-150">Beispiel</span><span class="sxs-lookup"><span data-stu-id="93a8e-150">Example</span></span>  
 <span data-ttu-id="93a8e-151">Das folgende Beispiel zeigt, wie Informationen zu einer Assembly bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="93a8e-151">The following example shows how to provide information about an assembly.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="93a8e-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93a8e-152">See also</span></span>

- [<span data-ttu-id="93a8e-153">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="93a8e-153">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="93a8e-154">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="93a8e-154">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="93a8e-155">Umleiten von Assemblyversionen</span><span class="sxs-lookup"><span data-stu-id="93a8e-155">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
