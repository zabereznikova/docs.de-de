---
title: '&lt;System.CodeDom&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom
helpviewer_keywords:
- compiler configuration elements, <system.codedom> element
- system.codedom element
- <system.codedom> element
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
ms.openlocfilehash: 1a97b20ae1f4e5c85d678f559cf0f7d69cfff4e1
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083950"
---
# <a name="ltsystemcodedomgt-element"></a><span data-ttu-id="ce5d7-102">&lt;System.CodeDom&gt; Element</span><span class="sxs-lookup"><span data-stu-id="ce5d7-102">&lt;system.codedom&gt; Element</span></span>
<span data-ttu-id="ce5d7-103">Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="ce5d7-103">Specifies compiler configuration settings for available language providers.</span></span>  
  
 <span data-ttu-id="ce5d7-104">\<Configuration >-Element</span><span class="sxs-lookup"><span data-stu-id="ce5d7-104">\<configuration> Element</span></span>  
<span data-ttu-id="ce5d7-105">\<System.CodeDom >-Element</span><span class="sxs-lookup"><span data-stu-id="ce5d7-105">\<system.codedom> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce5d7-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce5d7-106">Syntax</span></span>  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce5d7-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ce5d7-107">Attributes and Elements</span></span>  
 <span data-ttu-id="ce5d7-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ce5d7-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce5d7-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="ce5d7-109">Attributes</span></span>  
 <span data-ttu-id="ce5d7-110">Keine</span><span class="sxs-lookup"><span data-stu-id="ce5d7-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ce5d7-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ce5d7-111">Child Elements</span></span>  
  
|<span data-ttu-id="ce5d7-112">Element</span><span class="sxs-lookup"><span data-stu-id="ce5d7-112">Element</span></span>|<span data-ttu-id="ce5d7-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce5d7-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce5d7-114">\<compilers></span><span class="sxs-lookup"><span data-stu-id="ce5d7-114">\<compilers></span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="ce5d7-115">Der Container für Compilerkonfigurationselemente, dieser enthält 0 (null) oder mehr [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="ce5d7-115">Container for compiler configuration elements; contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ce5d7-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ce5d7-116">Parent Elements</span></span>  
  
|<span data-ttu-id="ce5d7-117">Element</span><span class="sxs-lookup"><span data-stu-id="ce5d7-117">Element</span></span>|<span data-ttu-id="ce5d7-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce5d7-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ce5d7-119">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ce5d7-119">\<configuration></span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="ce5d7-120">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="ce5d7-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce5d7-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ce5d7-121">Remarks</span></span>  
  
## <a name="net-framework-version-20"></a><span data-ttu-id="ce5d7-122">.NET Framework Version 2.0</span><span class="sxs-lookup"><span data-stu-id="ce5d7-122">.NET Framework Version 2.0</span></span>  
 <span data-ttu-id="ce5d7-123">Die [ \<system.codedom >](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) Element enthält die compilerkonfigurationseinstellungen für Sprachanbieter installiert, die auf einem Computer zusätzlich zu den Standardanbieter, die mit .NET Framework, z. B. installiert sind die <xref:Microsoft.CSharp.CSharpCodeProvider> und <xref:Microsoft.VisualBasic.VBCodeProvider>.</span><span class="sxs-lookup"><span data-stu-id="ce5d7-123">The [\<system.codedom>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) element contains compiler configuration settings for language providers installed on a computer in addition to the default providers that are installed with the .NET Framework, such as the <xref:Microsoft.CSharp.CSharpCodeProvider> and the <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span> <span data-ttu-id="ce5d7-124">Die [ \<Compiler >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) -Element enthält 0 (null) oder mehrere [ \<Compiler >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) Elemente.</span><span class="sxs-lookup"><span data-stu-id="ce5d7-124">The [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span> <span data-ttu-id="ce5d7-125">Jede [ \<Compiler >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) Element gibt die compilerkonfigurationsattribute für einen bestimmten Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="ce5d7-125">Each [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="ce5d7-126">Entwickler und Compileranbieter können Konfigurationseinstellungen hinzufügen, der Computerkonfigurationsdatei (Machine.config) für einen neuen <xref:System.CodeDom.Compiler.CodeDomProvider> Implementierung.</span><span class="sxs-lookup"><span data-stu-id="ce5d7-126">Developers and compiler vendors can add configuration settings to the machine configuration file (Machine.config) for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="ce5d7-127">Verwenden der <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> Methode, um die Standardanbieter für die Sprache und den Sprachanbieter identifizierte die compilereinstellungen für die Konfiguration auf einem Computer programmgesteuert aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="ce5d7-127">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate both the default language providers and language providers identified by the compiler configuration settings on a computer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce5d7-128">In .NET Framework, Version 1.0 und 1.1 wird die Standardsprache, die von .NET Framework bereitgestellten, in identifiziert werden der [ \<Compiler >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) Element.</span><span class="sxs-lookup"><span data-stu-id="ce5d7-128">In the .NET Framework versions 1.0 and 1.1, the default language providers supplied by the .NET Framework are identified in the [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element.</span></span> <span data-ttu-id="ce5d7-129">In .NET Framework, Version 2.0, werden die Standardanbieter für die Sprache nicht identifiziert die [ \<Compiler >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) -Element, jedoch mithilfe einer der <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="ce5d7-129">In the .NET Framework version 2.0, the default language providers are not identified in the [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element, but can be enumerated using the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> method.</span></span>  
  
## <a name="net-framework-versions-10-and-11"></a><span data-ttu-id="ce5d7-130">.NET Framework-Versionen 1.0 und 1.1</span><span class="sxs-lookup"><span data-stu-id="ce5d7-130">.NET Framework Versions 1.0 and 1.1</span></span>  
 <span data-ttu-id="ce5d7-131">Die [ \<system.codedom >](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) Element enthält die compilerkonfigurationseinstellungen für Sprachanbieter auf einem Computer.</span><span class="sxs-lookup"><span data-stu-id="ce5d7-131">The [\<system.codedom>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="ce5d7-132">Die [ \<Compiler >](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) -Element enthält 0 (null) oder mehrere [ \<Compiler >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) Elemente.</span><span class="sxs-lookup"><span data-stu-id="ce5d7-132">The [\<compilers>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md) element contains zero or more [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) elements.</span></span> <span data-ttu-id="ce5d7-133">Jede [ \<Compiler >](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) Element gibt die compilerkonfigurationsattribute für einen bestimmten Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="ce5d7-133">Each [\<compiler>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="ce5d7-134">.NET Framework definiert die ursprünglichen Compilereinstellungen in der Computerkonfigurationsdatei (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="ce5d7-134">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="ce5d7-135">Entwickler und Compileranbieter können Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider>-Implementierung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ce5d7-135">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="ce5d7-136">Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType>-Methode, um Sprachanbieter und Compilerkonfigurationseinstellungen auf einem Computer programmgesteuert aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="ce5d7-136">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="ce5d7-137">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="ce5d7-137">Configuration File</span></span>  
 <span data-ttu-id="ce5d7-138">Dieses Element kann in der Konfigurationsdatei des Computers und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ce5d7-138">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce5d7-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ce5d7-139">Example</span></span>  
 <span data-ttu-id="ce5d7-140">Das folgende Beispiel veranschaulicht eine typische Compilerkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="ce5d7-140">The following example illustrates a typical compiler configuration.</span></span>  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler   
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=1.0.5000.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions=""  
        warningLevel="1" />  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ce5d7-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce5d7-141">See also</span></span>
- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="ce5d7-142">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="ce5d7-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="ce5d7-143">Compiler and Language Provider Settings Schema (Schema für Compiler- und Sprachanbietereinstellungen)</span><span class="sxs-lookup"><span data-stu-id="ce5d7-143">Compiler and Language Provider Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/index.md)
- [<span data-ttu-id="ce5d7-144">\<compiler> Element</span><span class="sxs-lookup"><span data-stu-id="ce5d7-144">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)
