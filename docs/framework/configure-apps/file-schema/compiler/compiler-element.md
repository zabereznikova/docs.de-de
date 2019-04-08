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
ms.openlocfilehash: 34753d538ff37ac4ae621f653d47ac92ac6749a0
ms.sourcegitcommit: b8ace47d839f943f785b89e2fff8092b0bf8f565
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2019
ms.locfileid: "55674463"
---
# <a name="compiler-element"></a><span data-ttu-id="67917-102">\<Compilerfehler >-Element</span><span class="sxs-lookup"><span data-stu-id="67917-102">\<compiler> Element</span></span>

<span data-ttu-id="67917-103">Gibt die Compilerkonfigurationsattribute für einen Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="67917-103">Specifies the compiler configuration attributes for a language provider.</span></span>

<span data-ttu-id="67917-104">\<Configuration-Element > \<system.codedom-Element > \<Compilers-Element > \<Compiler > Element</span><span class="sxs-lookup"><span data-stu-id="67917-104">\<configuration Element> \<system.codedom Element> \<compilers Element> \<compiler> Element</span></span>

## <a name="syntax"></a><span data-ttu-id="67917-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="67917-105">Syntax</span></span>

```xml
<compiler
  language="languageName[;...;...]"
  extension="fileExtension[;...;...]"
  type="typeName, assemblyName"
  warningLevel="number"
  compilerOptions="option1 option2"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="67917-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="67917-106">Attributes and Elements</span></span>

<span data-ttu-id="67917-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="67917-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="67917-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="67917-108">Attributes</span></span>

|<span data-ttu-id="67917-109">Attribut</span><span class="sxs-lookup"><span data-stu-id="67917-109">Attribute</span></span>|<span data-ttu-id="67917-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="67917-110">Description</span></span>|
|---------------|-----------------|
|`compilerOptions`|<span data-ttu-id="67917-111">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="67917-111">Optional attribute.</span></span><br /><br /> <span data-ttu-id="67917-112">Gibt zusätzliche compilerspezifische Argumente für die Kompilierung an.</span><span class="sxs-lookup"><span data-stu-id="67917-112">Specifies additional compiler-specific arguments for compilation.</span></span> <span data-ttu-id="67917-113">Die Werte für die `compilerOptions` Attribut finden Sie in der Regel in einem Compileroptionen-Thema für den Compiler.</span><span class="sxs-lookup"><span data-stu-id="67917-113">The values for the `compilerOptions` attribute are typically listed in a compiler options topic for the compiler.</span></span>|
|`extension`|<span data-ttu-id="67917-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="67917-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="67917-115">Enthält eine durch Semikolons getrennte Liste der Dateinamenerweiterungen, die von Quelldateien verwendet werden, für den Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="67917-115">Provides a semicolon-separated list of file name extensions used by source files for the language provider.</span></span> <span data-ttu-id="67917-116">Z. B. ". cs".</span><span class="sxs-lookup"><span data-stu-id="67917-116">For example, ".cs".</span></span>|
|`language`|<span data-ttu-id="67917-117">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="67917-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="67917-118">Enthält eine durch Semikolons getrennte Liste von vom Sprachanbieter unterstützten Sprachnamen.</span><span class="sxs-lookup"><span data-stu-id="67917-118">Provides a semicolon-separated list of language names supported by the language provider.</span></span> <span data-ttu-id="67917-119">Z. B. "C#; Cs; Csharp".</span><span class="sxs-lookup"><span data-stu-id="67917-119">For example, "c#;cs;csharp".</span></span>|
|`type`|<span data-ttu-id="67917-120">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="67917-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="67917-121">Gibt den Typnamen des Sprachanbieters, einschließlich des Namens der Assembly, die die anbieterimplementierung enthält.</span><span class="sxs-lookup"><span data-stu-id="67917-121">Specifies the type name of the language provider, including the name of the assembly containing the provider implementation.</span></span> <span data-ttu-id="67917-122">Der Typname muss die Anforderungen erfüllen [angeben vollständig gekennzeichneter Typnamen](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="67917-122">The type name must meet the requirements defined in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|
|`warningLevel`|<span data-ttu-id="67917-123">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="67917-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="67917-124">Gibt die Warnstufe des Compilers "Standard" an. Bestimmt die Ebene, die mit der des Sprachanbieters für compilerwarnungen als Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="67917-124">Specifies the default compiler warning level; determines the level at which the language provider treats compilation warnings as errors.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="67917-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="67917-125">Child Elements</span></span>

|<span data-ttu-id="67917-126">Element</span><span class="sxs-lookup"><span data-stu-id="67917-126">Element</span></span>|<span data-ttu-id="67917-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="67917-127">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="67917-128">\<"Provideroption" >-Element</span><span class="sxs-lookup"><span data-stu-id="67917-128">\<providerOption> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/provideroption-element.md)|<span data-ttu-id="67917-129">Gibt den Compilerfehler Version-Attribute für einen Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="67917-129">Specifies compiler version attributes for a language provider.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="67917-130">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="67917-130">Parent Elements</span></span>

|<span data-ttu-id="67917-131">Element</span><span class="sxs-lookup"><span data-stu-id="67917-131">Element</span></span>|<span data-ttu-id="67917-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="67917-132">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="67917-133">\<configuration> Element</span><span class="sxs-lookup"><span data-stu-id="67917-133">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="67917-134">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="67917-134">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|[<span data-ttu-id="67917-135">\<System.CodeDom >-Element</span><span class="sxs-lookup"><span data-stu-id="67917-135">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="67917-136">Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="67917-136">Specifies compiler configuration settings for available language providers.</span></span>|
|[<span data-ttu-id="67917-137">\<Compiler > Element</span><span class="sxs-lookup"><span data-stu-id="67917-137">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="67917-138">Container für compilerkonfigurationselemente; enthält 0 (null) oder mehr `<compiler>` Elemente.</span><span class="sxs-lookup"><span data-stu-id="67917-138">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="67917-139">Hinweise</span><span class="sxs-lookup"><span data-stu-id="67917-139">Remarks</span></span>

<span data-ttu-id="67917-140">Jede `<compiler>` Element gibt die compilerkonfigurationsattribute für einen bestimmten Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="67917-140">Each `<compiler>` element specifies the compiler configuration attributes for a specific language provider.</span></span> <span data-ttu-id="67917-141">Der Datenanbieter erweitert die <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> -Klasse für eine bestimmte Sprache; der `<compiler>` -Element definiert den Compiler und den Code-Generator-Einstellungen für den Sprachanbieter.</span><span class="sxs-lookup"><span data-stu-id="67917-141">The provider extends the <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> class for a specific language; the `<compiler>` element defines the compiler and code generator settings for the language provider.</span></span>

<span data-ttu-id="67917-142">.NET Framework definiert die ursprünglichen Compilereinstellungen in der Computerkonfigurationsdatei (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="67917-142">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="67917-143">Entwickler und Compileranbieter können Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider>-Implementierung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="67917-143">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="67917-144">Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType>-Methode, um Sprachanbieter und Compilerkonfigurationseinstellungen auf einem Computer programmgesteuert aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="67917-144">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>

<span data-ttu-id="67917-145">Compilerfehler Elemente der Anwendungs-oder Webkonfigurationsdatei können ergänzen oder überschreiben die Einstellungen in der Computerkonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="67917-145">Compiler elements in the application or Web configuration file can supplement or override the settings in the machine configuration file.</span></span> <span data-ttu-id="67917-146">Wenn mehr als eine Implementierung eines Anbieters für den Namen der gleichen Sprache oder die gleiche Dateierweiterung konfiguriert ist, überschreibt die letzten übereinstimmende Konfiguration alle vorherigen konfigurierten Anbieter für diese Sprache oder die Erweiterung an.</span><span class="sxs-lookup"><span data-stu-id="67917-146">If more than one provider implementation is configured for the same language name or the same file extension, the last matching configuration overrides any previous configured providers for that language name or file extension.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="67917-147">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="67917-147">Configuration File</span></span>

<span data-ttu-id="67917-148">Dieses Element kann in der Konfigurationsdatei des Computers und der Anwendungskonfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="67917-148">This element can be used in the machine configuration file and the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="67917-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="67917-149">Example</span></span>

<span data-ttu-id="67917-150">Das folgende Beispiel veranschaulicht ein typisches Compilerkonfigurationselement:</span><span class="sxs-lookup"><span data-stu-id="67917-150">The following example illustrates a typical compiler configuration element:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="67917-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67917-151">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="67917-152">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="67917-152">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="67917-153">\<Compiler > Element</span><span class="sxs-lookup"><span data-stu-id="67917-153">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)
- [<span data-ttu-id="67917-154">Specifying Fully Qualified Type Names (Angeben vollqualifizierter Typnamen)</span><span class="sxs-lookup"><span data-stu-id="67917-154">Specifying Fully Qualified Type Names</span></span>](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="67917-155">[Compiler-Element für Compilers für Compilation ((ASP.NET Einstellungsschema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="67917-155">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
