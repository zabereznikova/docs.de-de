---
title: <compiler>-Element
ms.date: 08/14/2018
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#compiler
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.codedom/compilers/compiler
helpviewer_keywords:
- compiler configuration elements, <compiler> element
- <compiler> element
- compiler configuration attributes
- compiler element
ms.assetid: 7a151659-b803-4c27-b5ce-1c4aa0d5a823
ms.openlocfilehash: a19cf8182cdb338fd8596ef38311916de0daae37
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2019
ms.locfileid: "70168938"
---
# <a name="compiler-element"></a><span data-ttu-id="72e1f-102">\<Compiler > Element</span><span class="sxs-lookup"><span data-stu-id="72e1f-102">\<compiler> Element</span></span>

<span data-ttu-id="72e1f-103">Gibt die Compilerkonfigurationsattribute für einen Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="72e1f-103">Specifies the compiler configuration attributes for a language provider.</span></span>

[<span data-ttu-id="72e1f-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="72e1f-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="72e1f-105">&nbsp;&nbsp;[ **\<System. CodeDom->** ](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="72e1f-105">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span></span>  
<span data-ttu-id="72e1f-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Compiler >** ](compilers-element.md)</span><span class="sxs-lookup"><span data-stu-id="72e1f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)</span></span>  
<span data-ttu-id="72e1f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Compiler>**</span><span class="sxs-lookup"><span data-stu-id="72e1f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compiler>**</span></span>  

## <a name="syntax"></a><span data-ttu-id="72e1f-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="72e1f-108">Syntax</span></span>

```xml
<compiler
  language="languageName[;...;...]"
  extension="fileExtension[;...;...]"
  type="typeName, assemblyName"
  warningLevel="number"
  compilerOptions="option1 option2"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="72e1f-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="72e1f-109">Attributes and Elements</span></span>

<span data-ttu-id="72e1f-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="72e1f-110">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="72e1f-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="72e1f-111">Attributes</span></span>

|<span data-ttu-id="72e1f-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="72e1f-112">Attribute</span></span>|<span data-ttu-id="72e1f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72e1f-113">Description</span></span>|
|---------------|-----------------|
|`compilerOptions`|<span data-ttu-id="72e1f-114">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="72e1f-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="72e1f-115">Gibt zusätzliche compilerspezifische Argumente für die Kompilierung an.</span><span class="sxs-lookup"><span data-stu-id="72e1f-115">Specifies additional compiler-specific arguments for compilation.</span></span> <span data-ttu-id="72e1f-116">Die Werte für das `compilerOptions` -Attribut werden in der Regel in einem Compileroptionen-Thema für den Compiler aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="72e1f-116">The values for the `compilerOptions` attribute are typically listed in a compiler options topic for the compiler.</span></span>|
|`extension`|<span data-ttu-id="72e1f-117">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="72e1f-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="72e1f-118">Stellt eine durch Semikolons getrennte Liste der Dateinamen Erweiterungen bereit, die von den Quelldateien für den Sprachanbieter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="72e1f-118">Provides a semicolon-separated list of file name extensions used by source files for the language provider.</span></span> <span data-ttu-id="72e1f-119">Beispiel: ". cs".</span><span class="sxs-lookup"><span data-stu-id="72e1f-119">For example, ".cs".</span></span>|
|`language`|<span data-ttu-id="72e1f-120">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="72e1f-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="72e1f-121">Stellt eine durch Semikolons getrennte Liste der vom Sprachanbieter unterstützten Sprachnamen bereit.</span><span class="sxs-lookup"><span data-stu-id="72e1f-121">Provides a semicolon-separated list of language names supported by the language provider.</span></span> <span data-ttu-id="72e1f-122">Beispiel: "c#; cs; csharp".</span><span class="sxs-lookup"><span data-stu-id="72e1f-122">For example, "c#;cs;csharp".</span></span>|
|`type`|<span data-ttu-id="72e1f-123">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="72e1f-123">Required attribute.</span></span><br /><br /> <span data-ttu-id="72e1f-124">Gibt den Typnamen des sprach Anbieters an, einschließlich des Namens der Assembly, die die Anbieter Implementierung enthält.</span><span class="sxs-lookup"><span data-stu-id="72e1f-124">Specifies the type name of the language provider, including the name of the assembly containing the provider implementation.</span></span> <span data-ttu-id="72e1f-125">Der Typname muss die in [Angeben von voll qualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)definierten Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="72e1f-125">The type name must meet the requirements defined in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|
|`warningLevel`|<span data-ttu-id="72e1f-126">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="72e1f-126">Optional attribute.</span></span><br /><br /> <span data-ttu-id="72e1f-127">Gibt die Standard-compilerwartebene an. bestimmt die Ebene, auf der der Sprachanbieter Kompilierungs Warnungen als Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="72e1f-127">Specifies the default compiler warning level; determines the level at which the language provider treats compilation warnings as errors.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="72e1f-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="72e1f-128">Child Elements</span></span>

|<span data-ttu-id="72e1f-129">Element</span><span class="sxs-lookup"><span data-stu-id="72e1f-129">Element</span></span>|<span data-ttu-id="72e1f-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72e1f-130">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="72e1f-131">\<Provideroption >-Element</span><span class="sxs-lookup"><span data-stu-id="72e1f-131">\<providerOption> Element</span></span>](provideroption-element.md)|<span data-ttu-id="72e1f-132">Gibt Attribute der Compilerversion für einen Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="72e1f-132">Specifies compiler version attributes for a language provider.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="72e1f-133">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="72e1f-133">Parent Elements</span></span>

|<span data-ttu-id="72e1f-134">Element</span><span class="sxs-lookup"><span data-stu-id="72e1f-134">Element</span></span>|<span data-ttu-id="72e1f-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72e1f-135">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="72e1f-136">\<configuration> Element</span><span class="sxs-lookup"><span data-stu-id="72e1f-136">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="72e1f-137">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="72e1f-137">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|[<span data-ttu-id="72e1f-138">\<System. CodeDom >-Element</span><span class="sxs-lookup"><span data-stu-id="72e1f-138">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="72e1f-139">Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="72e1f-139">Specifies compiler configuration settings for available language providers.</span></span>|
|[<span data-ttu-id="72e1f-140">\<Compiler > Element</span><span class="sxs-lookup"><span data-stu-id="72e1f-140">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="72e1f-141">Container für Compilerkonfigurationselemente; enthält 0 (NULL `<compiler>` ) oder mehr-Elemente.</span><span class="sxs-lookup"><span data-stu-id="72e1f-141">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="72e1f-142">Hinweise</span><span class="sxs-lookup"><span data-stu-id="72e1f-142">Remarks</span></span>

<span data-ttu-id="72e1f-143">Jedes `<compiler>` -Element gibt die Compilerkonfigurationsattribute für einen bestimmten Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="72e1f-143">Each `<compiler>` element specifies the compiler configuration attributes for a specific language provider.</span></span> <span data-ttu-id="72e1f-144">Der Anbieter erweitert die <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> -Klasse für eine bestimmte Sprache; `<compiler>` das-Element definiert die Compiler-und Code-Generator-Einstellungen für den Sprachanbieter.</span><span class="sxs-lookup"><span data-stu-id="72e1f-144">The provider extends the <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> class for a specific language; the `<compiler>` element defines the compiler and code generator settings for the language provider.</span></span>

<span data-ttu-id="72e1f-145">.NET Framework definiert die ursprünglichen Compilereinstellungen in der Computerkonfigurationsdatei (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="72e1f-145">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="72e1f-146">Entwickler und Compileranbieter können Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider>-Implementierung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="72e1f-146">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="72e1f-147">Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType>-Methode, um Sprachanbieter und Compilerkonfigurationseinstellungen auf einem Computer programmgesteuert aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="72e1f-147">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>

<span data-ttu-id="72e1f-148">Compilerelemente in der Anwendungs-oder Webkonfigurationsdatei können die Einstellungen in der Computer Konfigurationsdatei ergänzen oder überschreiben.</span><span class="sxs-lookup"><span data-stu-id="72e1f-148">Compiler elements in the application or Web configuration file can supplement or override the settings in the machine configuration file.</span></span> <span data-ttu-id="72e1f-149">Wenn mehr als eine Anbieter Implementierung für denselben Sprachnamen oder dieselbe Dateierweiterung konfiguriert ist, überschreibt die letzte übereinstimmende Konfiguration alle zuvor konfigurierten Anbieter für diesen Sprachnamen oder die Dateierweiterung.</span><span class="sxs-lookup"><span data-stu-id="72e1f-149">If more than one provider implementation is configured for the same language name or the same file extension, the last matching configuration overrides any previous configured providers for that language name or file extension.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="72e1f-150">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="72e1f-150">Configuration File</span></span>

<span data-ttu-id="72e1f-151">Dieses Element kann in der Computer Konfigurationsdatei und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="72e1f-151">This element can be used in the machine configuration file and the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="72e1f-152">Beispiel</span><span class="sxs-lookup"><span data-stu-id="72e1f-152">Example</span></span>

<span data-ttu-id="72e1f-153">Das folgende Beispiel veranschaulicht ein typisches compilerkonfigurationselement:</span><span class="sxs-lookup"><span data-stu-id="72e1f-153">The following example illustrates a typical compiler configuration element:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="72e1f-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72e1f-154">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="72e1f-155">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="72e1f-155">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="72e1f-156">\<Compiler > Element</span><span class="sxs-lookup"><span data-stu-id="72e1f-156">\<compilers> Element</span></span>](compilers-element.md)
- [<span data-ttu-id="72e1f-157">Specifying Fully Qualified Type Names (Angeben vollqualifizierter Typnamen)</span><span class="sxs-lookup"><span data-stu-id="72e1f-157">Specifying Fully Qualified Type Names</span></span>](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="72e1f-158">[Compiler-Element für Compiler für die Kompilierung (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="72e1f-158">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
