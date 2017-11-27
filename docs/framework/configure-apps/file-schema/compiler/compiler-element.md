---
title: '&lt;Compilerfehler&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler
helpviewer_keywords:
- compiler configuration elements, <compiler> element
- <compiler> element
- compiler configuration attributes
- compiler element
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
caps.latest.revision: "20"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 8d2562bb37413cd07b4548bbf2bad0b6a9aedbc5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltcompilergt-element"></a><span data-ttu-id="a5f38-102">&lt;Compilerfehler&gt; Element</span><span class="sxs-lookup"><span data-stu-id="a5f38-102">&lt;compiler&gt; Element</span></span>
<span data-ttu-id="a5f38-103">Gibt die Compilerkonfigurationsattribute für einen Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="a5f38-103">Specifies the compiler configuration attributes for a language provider.</span></span>  
  
 <span data-ttu-id="a5f38-104">\<Konfiguration-Element ></span><span class="sxs-lookup"><span data-stu-id="a5f38-104">\<configuration Element></span></span>  
<span data-ttu-id="a5f38-105">\<System.CodeDom-Element ></span><span class="sxs-lookup"><span data-stu-id="a5f38-105">\<system.codedom Element></span></span>  
<span data-ttu-id="a5f38-106">\<Compilers-Element ></span><span class="sxs-lookup"><span data-stu-id="a5f38-106">\<compilers Element></span></span>  
<span data-ttu-id="a5f38-107">\<Compilerfehler >-Element</span><span class="sxs-lookup"><span data-stu-id="a5f38-107">\<compiler> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5f38-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="a5f38-108">Syntax</span></span>  
  
```xml  
<compiler  
  language="languageName[;...;...]"  
  extension="fileExtension[;...;...]"  
  type="typeName, assemblyName"  
  warningLevel="number"  
  compilerOptions="option1 option2"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5f38-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a5f38-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a5f38-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a5f38-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5f38-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="a5f38-111">Attributes</span></span>  
  
|<span data-ttu-id="a5f38-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="a5f38-112">Attribute</span></span>|<span data-ttu-id="a5f38-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a5f38-113">Description</span></span>|  
|---------------|-----------------|  
|`compilerOptions`|<span data-ttu-id="a5f38-114">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="a5f38-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a5f38-115">Gibt zusätzliche compilerspezifisch Argumente für die Kompilierung an.</span><span class="sxs-lookup"><span data-stu-id="a5f38-115">Specifies additional compiler-specific arguments for compilation.</span></span> <span data-ttu-id="a5f38-116">Die Werte für die `compilerOptions` Attribut werden in der Regel in einem Compileroptionen-Thema für den Compiler aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="a5f38-116">The values for the `compilerOptions` attribute are typically listed in a compiler options topic for the compiler.</span></span> <span data-ttu-id="a5f38-117">In der Visual Studio 2005-Dokumentation können Sie die Optionen für den Compiler suchen, durch die Suche nach "Compileroptionen" im Index.</span><span class="sxs-lookup"><span data-stu-id="a5f38-117">In the Visual Studio 2005 documentation, you can locate the options for the compiler by looking for "compiler options" in the index.</span></span>|  
|`extension`|<span data-ttu-id="a5f38-118">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="a5f38-118">Required attribute.</span></span><br /><br /> <span data-ttu-id="a5f38-119">Enthält eine durch Semikolons getrennte Liste der Dateinamenerweiterungen, die von Quelldateien für das Language-Anbieter verwendet.</span><span class="sxs-lookup"><span data-stu-id="a5f38-119">Provides a semicolon-separated list of file name extensions used by source files for the language provider.</span></span> <span data-ttu-id="a5f38-120">Z. B. "cs".</span><span class="sxs-lookup"><span data-stu-id="a5f38-120">For example, ".cs".</span></span>|  
|`language`|<span data-ttu-id="a5f38-121">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="a5f38-121">Required attribute.</span></span><br /><br /> <span data-ttu-id="a5f38-122">Enthält eine durch Semikolons getrennte Liste der Sprachnamen, die von der Language-Anbieter unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a5f38-122">Provides a semicolon-separated list of language names supported by the language provider.</span></span> <span data-ttu-id="a5f38-123">Z. B. "c#; Cs; Csharp".</span><span class="sxs-lookup"><span data-stu-id="a5f38-123">For example, "c#;cs;csharp".</span></span>|  
|`type`|<span data-ttu-id="a5f38-124">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="a5f38-124">Required attribute.</span></span><br /><br /> <span data-ttu-id="a5f38-125">Gibt den Typnamen des Sprachanbieters, einschließlich des Namens der Assembly, die die Implementierung eines Anbieters enthält.</span><span class="sxs-lookup"><span data-stu-id="a5f38-125">Specifies the type name of the language provider, including the name of the assembly containing the provider implementation.</span></span> <span data-ttu-id="a5f38-126">Der Typname muss die Anforderungen erfüllen [angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="a5f38-126">The type name must meet the requirements defined in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`warningLevel`|<span data-ttu-id="a5f38-127">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="a5f38-127">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a5f38-128">Gibt die Warnstufe für Standard-Compiler. Bestimmt die Ebene an, an der der Sprachanbieter Kompilierung Warnungen als Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="a5f38-128">Specifies the default compiler warning level; determines the level at which the language provider treats compilation warnings as errors.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a5f38-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a5f38-129">Child Elements</span></span>  
  
|<span data-ttu-id="a5f38-130">Element</span><span class="sxs-lookup"><span data-stu-id="a5f38-130">Element</span></span>|<span data-ttu-id="a5f38-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a5f38-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a5f38-132">\<"Provideroption" >-Element</span><span class="sxs-lookup"><span data-stu-id="a5f38-132">\<providerOption> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/provideroption-element.md)|<span data-ttu-id="a5f38-133">Gibt die Version Compilerattribute für einen Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="a5f38-133">Specifies compiler version attributes for a language provider.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a5f38-134">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a5f38-134">Parent Elements</span></span>  
  
|<span data-ttu-id="a5f38-135">Element</span><span class="sxs-lookup"><span data-stu-id="a5f38-135">Element</span></span>|<span data-ttu-id="a5f38-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a5f38-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a5f38-137">\<configuration>-Element</span><span class="sxs-lookup"><span data-stu-id="a5f38-137">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="a5f38-138">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="a5f38-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="a5f38-139">\<System.CodeDom > Element</span><span class="sxs-lookup"><span data-stu-id="a5f38-139">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="a5f38-140">Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="a5f38-140">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="a5f38-141">\<Compiler >-Element</span><span class="sxs-lookup"><span data-stu-id="a5f38-141">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="a5f38-142">Container für compilerkonfigurationselemente; enthält 0 (null) oder mehrere `<compiler>` Elemente.</span><span class="sxs-lookup"><span data-stu-id="a5f38-142">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5f38-143">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a5f38-143">Remarks</span></span>  
 <span data-ttu-id="a5f38-144">Jede `<compiler>` Element gibt die compilerkonfigurationsattribute für eine bestimmte Sprache-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="a5f38-144">Each `<compiler>` element specifies the compiler configuration attributes for a specific language provider.</span></span> <span data-ttu-id="a5f38-145">Der Anbieter erweitert die <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> Klasse für eine bestimmte Sprache; die `<compiler>` -Element definiert den Compiler und den Code-Generator-Einstellungen für den Sprachanbieter.</span><span class="sxs-lookup"><span data-stu-id="a5f38-145">The provider extends the <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> class for a specific language; the `<compiler>` element defines the compiler and code generator settings for the language provider.</span></span>  
  
 <span data-ttu-id="a5f38-146">.NET Framework definiert die ursprünglichen Compilereinstellungen in der Computerkonfigurationsdatei (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="a5f38-146">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="a5f38-147">Entwickler und Compileranbieter können Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider>-Implementierung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a5f38-147">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="a5f38-148">Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType>-Methode, um Sprachanbieter und Compilerkonfigurationseinstellungen auf einem Computer programmgesteuert aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="a5f38-148">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
 <span data-ttu-id="a5f38-149">Compilerfehler Elemente in der Anwendungs- oder Webkonfigurationsdatei können ergänzen oder diesen überschreiben die Einstellungen in der Computerkonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="a5f38-149">Compiler elements in the application or Web configuration file can supplement or override the settings in the machine configuration file.</span></span> <span data-ttu-id="a5f38-150">Wenn mehr als eine Implementierung eines Anbieters für den gleichen Sprachenname oder der gleichen Erweiterung konfiguriert ist, überschreibt die letzten übereinstimmende Konfiguration alle vorherigen konfigurierten Anbieter für diese Sprache oder die Erweiterung an.</span><span class="sxs-lookup"><span data-stu-id="a5f38-150">If more than one provider implementation is configured for the same language name or the same file extension, the last matching configuration overrides any previous configured providers for that language name or file extension.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="a5f38-151">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="a5f38-151">Configuration File</span></span>  
 <span data-ttu-id="a5f38-152">Dieses Element kann in der Computerkonfigurationsdatei und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a5f38-152">This element can be used in the machine configuration file and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5f38-153">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a5f38-153">Example</span></span>  
 <span data-ttu-id="a5f38-154">Das folgende Beispiel veranschaulicht ein typisches Compilerkonfigurationselement.</span><span class="sxs-lookup"><span data-stu-id="a5f38-154">The following example illustrates a typical compiler configuration element.</span></span>  
  
```xml  
<configuration>  
  <system.codedom>  
    <compilers>  
      <!-- zero or more compiler elements -->  
      <compiler  
        language="c#;cs;csharp"  
        extension=".cs"  
        type="Microsoft.CSharp.CSharpCodeProvider, System,   
          Version=2.0.3600.0, Culture=neutral,   
          PublicKeyToken=b77a5c561934e089"  
        compilerOptions="/optimize"  
        warningLevel="1" />  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a5f38-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5f38-155">See Also</span></span>  
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [<span data-ttu-id="a5f38-156">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="a5f38-156">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="a5f38-157">\<Compiler >-Element</span><span class="sxs-lookup"><span data-stu-id="a5f38-157">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
 [<span data-ttu-id="a5f38-158">Specifying Fully Qualified Type Names (Angeben vollqualifizierter Typnamen)</span><span class="sxs-lookup"><span data-stu-id="a5f38-158">Specifying Fully Qualified Type Names</span></span>](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)  
 [<span data-ttu-id="a5f38-159">Compiler-Element für Compiler für Kompilierung ((ASP.NET Settings Schema)</span><span class="sxs-lookup"><span data-stu-id="a5f38-159">compiler Element for compilers for compilation (ASP.NET Settings Schema)</span></span>](http://msdn.microsoft.com/en-us/f7d6b078-5d42-4134-b3f7-62e1aba1df1e)
