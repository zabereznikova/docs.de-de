---
title: <system.codedom>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.codedom
helpviewer_keywords:
- compiler configuration elements, <system.codedom> element
- system.codedom element
- <system.codedom> element
ms.assetid: 672a68f7-e69f-4479-ac30-e980085ec4fe
ms.openlocfilehash: 40a3c84e1deed4d215383670176623a6a79ac41d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155387"
---
# <a name="systemcodedom-element"></a><span data-ttu-id="cc7c5-102">\<system.codedom> Element</span><span class="sxs-lookup"><span data-stu-id="cc7c5-102">\<system.codedom> Element</span></span>
<span data-ttu-id="cc7c5-103">Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="cc7c5-103">Specifies compiler configuration settings for available language providers.</span></span>  
  
[<span data-ttu-id="cc7c5-104">**\<Konfiguration>**</span><span class="sxs-lookup"><span data-stu-id="cc7c5-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="cc7c5-105">&nbsp;&nbsp;**\<system.codedom>**</span><span class="sxs-lookup"><span data-stu-id="cc7c5-105">&nbsp;&nbsp;**\<system.codedom>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc7c5-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="cc7c5-106">Syntax</span></span>  
  
```xml  
<system.codedom>  
  <compilers> ... </compilers>  
</system.codedom>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cc7c5-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cc7c5-107">Attributes and Elements</span></span>  
 <span data-ttu-id="cc7c5-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cc7c5-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cc7c5-109">Attributes</span><span class="sxs-lookup"><span data-stu-id="cc7c5-109">Attributes</span></span>  
 <span data-ttu-id="cc7c5-110">Keine.</span><span class="sxs-lookup"><span data-stu-id="cc7c5-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cc7c5-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cc7c5-111">Child Elements</span></span>  
  
|<span data-ttu-id="cc7c5-112">Element</span><span class="sxs-lookup"><span data-stu-id="cc7c5-112">Element</span></span>|<span data-ttu-id="cc7c5-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc7c5-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc7c5-114">\<Compiler></span><span class="sxs-lookup"><span data-stu-id="cc7c5-114">\<compilers></span></span>](compilers-element.md)|<span data-ttu-id="cc7c5-115">Container für Compilerkonfigurationselemente; enthält null oder mehr [ \<Compiler>](compiler-element.md) Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="cc7c5-115">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cc7c5-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cc7c5-116">Parent Elements</span></span>  
  
|<span data-ttu-id="cc7c5-117">Element</span><span class="sxs-lookup"><span data-stu-id="cc7c5-117">Element</span></span>|<span data-ttu-id="cc7c5-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc7c5-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cc7c5-119">\<Konfiguration></span><span class="sxs-lookup"><span data-stu-id="cc7c5-119">\<configuration></span></span>](../configuration-element.md)|<span data-ttu-id="cc7c5-120">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="cc7c5-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc7c5-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="cc7c5-121">Remarks</span></span>  
  
## <a name="net-framework-version-20"></a><span data-ttu-id="cc7c5-122">.NET Framework Version 2.0</span><span class="sxs-lookup"><span data-stu-id="cc7c5-122">.NET Framework Version 2.0</span></span>  
 <span data-ttu-id="cc7c5-123">Das [ \<system.codedom>-Element](system-codedom-element.md) enthält Compilerkonfigurationseinstellungen für Sprachanbieter, die auf einem Computer installiert sind, zusätzlich <xref:Microsoft.CSharp.CSharpCodeProvider> zu <xref:Microsoft.VisualBasic.VBCodeProvider>den Standardanbietern, die mit .NET Framework installiert sind, z. B. die und die .</span><span class="sxs-lookup"><span data-stu-id="cc7c5-123">The [\<system.codedom>](system-codedom-element.md) element contains compiler configuration settings for language providers installed on a computer in addition to the default providers that are installed with the .NET Framework, such as the <xref:Microsoft.CSharp.CSharpCodeProvider> and the <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span> <span data-ttu-id="cc7c5-124">Die [ \<Compiler>](compilers-element.md) Element enthält null oder mehr [ \<Compiler>](compiler-element.md) Elemente.</span><span class="sxs-lookup"><span data-stu-id="cc7c5-124">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="cc7c5-125">Jeder [ \<Compiler>-Element](compiler-element.md) die Compilerkonfigurationsattribute für einen bestimmten Sprachanbieter angibt.</span><span class="sxs-lookup"><span data-stu-id="cc7c5-125">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="cc7c5-126">Entwickler und Compilerhersteller können der Computerkonfigurationsdatei (Machine.config) Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider> Implementierung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cc7c5-126">Developers and compiler vendors can add configuration settings to the machine configuration file (Machine.config) for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="cc7c5-127">Verwenden <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> Sie die Methode, um sowohl die Standardsprachanbieter als auch die Sprachanbieter, die durch die Compilerkonfigurationseinstellungen auf einem Computer identifiziert werden, programmgesteuert aufzuzählen.</span><span class="sxs-lookup"><span data-stu-id="cc7c5-127">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate both the default language providers and language providers identified by the compiler configuration settings on a computer.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cc7c5-128">In den .NET Framework-Versionen 1.0 und 1.1 werden die von .NET Framework bereitgestellten Standardsprachenanbieter in den [ \<Compilern>-Element](compilers-element.md) identifiziert.</span><span class="sxs-lookup"><span data-stu-id="cc7c5-128">In the .NET Framework versions 1.0 and 1.1, the default language providers supplied by the .NET Framework are identified in the [\<compilers>](compilers-element.md) element.</span></span> <span data-ttu-id="cc7c5-129">In .NET Framework Version 2.0 werden die Standardsprachanbieter nicht in den <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> [ \<Compilern identifiziert>-Element,](compilers-element.md) sondern können mit der Methode aufgezählt werden.</span><span class="sxs-lookup"><span data-stu-id="cc7c5-129">In the .NET Framework version 2.0, the default language providers are not identified in the [\<compilers>](compilers-element.md) element, but can be enumerated using the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A> method.</span></span>  
  
## <a name="net-framework-versions-10-and-11"></a><span data-ttu-id="cc7c5-130">.NET Framework-Versionen 1.0 und 1.1</span><span class="sxs-lookup"><span data-stu-id="cc7c5-130">.NET Framework Versions 1.0 and 1.1</span></span>  
 <span data-ttu-id="cc7c5-131">Das [ \<system.codedom>-Element](system-codedom-element.md) enthält die Compilerkonfigurationseinstellungen für Sprachanbieter auf einem Computer.</span><span class="sxs-lookup"><span data-stu-id="cc7c5-131">The [\<system.codedom>](system-codedom-element.md) element contains the compiler configuration settings for language providers on a computer.</span></span> <span data-ttu-id="cc7c5-132">Die [ \<Compiler>](compilers-element.md) Element enthält null oder mehr [ \<Compiler>](compiler-element.md) Elemente.</span><span class="sxs-lookup"><span data-stu-id="cc7c5-132">The [\<compilers>](compilers-element.md) element contains zero or more [\<compiler>](compiler-element.md) elements.</span></span> <span data-ttu-id="cc7c5-133">Jeder [ \<Compiler>-Element](compiler-element.md) die Compilerkonfigurationsattribute für einen bestimmten Sprachanbieter angibt.</span><span class="sxs-lookup"><span data-stu-id="cc7c5-133">Each [\<compiler>](compiler-element.md) element specifies the compiler configuration attributes for a specific language provider.</span></span>  
  
 <span data-ttu-id="cc7c5-134">.NET Framework definiert die ursprünglichen Compilereinstellungen in der Computerkonfigurationsdatei (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="cc7c5-134">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="cc7c5-135">Entwickler und Compileranbieter können Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider>-Implementierung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cc7c5-135">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="cc7c5-136">Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType>-Methode, um Sprachanbieter und Compilerkonfigurationseinstellungen auf einem Computer programmgesteuert aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="cc7c5-136">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="cc7c5-137">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="cc7c5-137">Configuration File</span></span>  
 <span data-ttu-id="cc7c5-138">Dieses Element kann in der Maschinenkonfigurationsdatei und in der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cc7c5-138">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc7c5-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cc7c5-139">Example</span></span>  
 <span data-ttu-id="cc7c5-140">Das folgende Beispiel veranschaulicht eine typische Compilerkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="cc7c5-140">The following example illustrates a typical compiler configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cc7c5-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cc7c5-141">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="cc7c5-142">Schema der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="cc7c5-142">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="cc7c5-143">Compiler- und Sprachanbietereinstellungen Schema</span><span class="sxs-lookup"><span data-stu-id="cc7c5-143">Compiler and Language Provider Settings Schema</span></span>](index.md)
- [<span data-ttu-id="cc7c5-144">\<Compiler> Element</span><span class="sxs-lookup"><span data-stu-id="cc7c5-144">\<compiler> Element</span></span>](compiler-element.md)
