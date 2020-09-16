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
ms.openlocfilehash: 0abbe594754cbd70ec4732a1e7ef98e8e88bf167
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544751"
---
# <a name="compiler-element"></a><span data-ttu-id="ef1de-102">\<compiler>-Element</span><span class="sxs-lookup"><span data-stu-id="ef1de-102">\<compiler> Element</span></span>

<span data-ttu-id="ef1de-103">Gibt die Compilerkonfigurationsattribute für einen Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="ef1de-103">Specifies the compiler configuration attributes for a language provider.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compiler>**

## <a name="syntax"></a><span data-ttu-id="ef1de-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ef1de-104">Syntax</span></span>

```xml
<compiler
  language="languageName[;...;...]"
  extension="fileExtension[;...;...]"
  type="typeName, assemblyName"
  warningLevel="number"
  compilerOptions="option1 option2"
/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ef1de-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ef1de-105">Attributes and Elements</span></span>

<span data-ttu-id="ef1de-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ef1de-106">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="ef1de-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="ef1de-107">Attributes</span></span>

|<span data-ttu-id="ef1de-108">attribute</span><span class="sxs-lookup"><span data-stu-id="ef1de-108">Attribute</span></span>|<span data-ttu-id="ef1de-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ef1de-109">Description</span></span>|
|---------------|-----------------|
|`compilerOptions`|<span data-ttu-id="ef1de-110">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="ef1de-110">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ef1de-111">Gibt zusätzliche compilerspezifische Argumente für die Kompilierung an.</span><span class="sxs-lookup"><span data-stu-id="ef1de-111">Specifies additional compiler-specific arguments for compilation.</span></span> <span data-ttu-id="ef1de-112">Die Werte für das- `compilerOptions` Attribut werden in der Regel in einem Compileroptionen-Thema für den Compiler aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="ef1de-112">The values for the `compilerOptions` attribute are typically listed in a compiler options topic for the compiler.</span></span>|
|`extension`|<span data-ttu-id="ef1de-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="ef1de-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="ef1de-114">Stellt eine durch Semikolons getrennte Liste der Dateinamen Erweiterungen bereit, die von den Quelldateien für den Sprachanbieter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ef1de-114">Provides a semicolon-separated list of file name extensions used by source files for the language provider.</span></span> <span data-ttu-id="ef1de-115">Beispiel: ".cs".</span><span class="sxs-lookup"><span data-stu-id="ef1de-115">For example, ".cs".</span></span>|
|`language`|<span data-ttu-id="ef1de-116">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="ef1de-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="ef1de-117">Stellt eine durch Semikolons getrennte Liste der vom Sprachanbieter unterstützten Sprachnamen bereit.</span><span class="sxs-lookup"><span data-stu-id="ef1de-117">Provides a semicolon-separated list of language names supported by the language provider.</span></span> <span data-ttu-id="ef1de-118">Beispiel: "C#;cs;csharp".</span><span class="sxs-lookup"><span data-stu-id="ef1de-118">For example, "c#;cs;csharp".</span></span>|
|`type`|<span data-ttu-id="ef1de-119">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="ef1de-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="ef1de-120">Gibt den Typnamen des sprach Anbieters an, einschließlich des Namens der Assembly, die die Anbieter Implementierung enthält.</span><span class="sxs-lookup"><span data-stu-id="ef1de-120">Specifies the type name of the language provider, including the name of the assembly containing the provider implementation.</span></span> <span data-ttu-id="ef1de-121">Der Typname muss die in [Angeben von voll qualifizierten Typnamen](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)definierten Anforderungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="ef1de-121">The type name must meet the requirements defined in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|
|`warningLevel`|<span data-ttu-id="ef1de-122">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="ef1de-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ef1de-123">Gibt die Standard-compilerwartebene an. bestimmt die Ebene, auf der der Sprachanbieter Kompilierungs Warnungen als Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="ef1de-123">Specifies the default compiler warning level; determines the level at which the language provider treats compilation warnings as errors.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="ef1de-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ef1de-124">Child Elements</span></span>

|<span data-ttu-id="ef1de-125">Element</span><span class="sxs-lookup"><span data-stu-id="ef1de-125">Element</span></span>|<span data-ttu-id="ef1de-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ef1de-126">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ef1de-127">\<providerOption>-Element</span><span class="sxs-lookup"><span data-stu-id="ef1de-127">\<providerOption> Element</span></span>](provideroption-element.md)|<span data-ttu-id="ef1de-128">Gibt Attribute der Compilerversion für einen Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="ef1de-128">Specifies compiler version attributes for a language provider.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ef1de-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ef1de-129">Parent Elements</span></span>

|<span data-ttu-id="ef1de-130">Element</span><span class="sxs-lookup"><span data-stu-id="ef1de-130">Element</span></span>|<span data-ttu-id="ef1de-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ef1de-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ef1de-132">\<configuration>-Element</span><span class="sxs-lookup"><span data-stu-id="ef1de-132">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="ef1de-133">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="ef1de-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|[<span data-ttu-id="ef1de-134">\<system.codedom>-Element</span><span class="sxs-lookup"><span data-stu-id="ef1de-134">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="ef1de-135">Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="ef1de-135">Specifies compiler configuration settings for available language providers.</span></span>|
|[<span data-ttu-id="ef1de-136">\<compilers>-Element</span><span class="sxs-lookup"><span data-stu-id="ef1de-136">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="ef1de-137">Container für Compilerkonfigurationselemente; enthält 0 (null) oder mehr- `<compiler>` Elemente.</span><span class="sxs-lookup"><span data-stu-id="ef1de-137">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ef1de-138">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ef1de-138">Remarks</span></span>

<span data-ttu-id="ef1de-139">Jedes- `<compiler>` Element gibt die Compilerkonfigurationsattribute für einen bestimmten Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="ef1de-139">Each `<compiler>` element specifies the compiler configuration attributes for a specific language provider.</span></span> <span data-ttu-id="ef1de-140">Der Anbieter erweitert die <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> -Klasse für eine bestimmte Sprache; das- `<compiler>` Element definiert die Compiler-und Code-Generator-Einstellungen für den Sprachanbieter.</span><span class="sxs-lookup"><span data-stu-id="ef1de-140">The provider extends the <xref:System.CodeDom.Compiler.CodeDomProvider?displayProperty=nameWithType> class for a specific language; the `<compiler>` element defines the compiler and code generator settings for the language provider.</span></span>

<span data-ttu-id="ef1de-141">.NET Framework definiert die ursprünglichen Compilereinstellungen in der Computerkonfigurationsdatei (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="ef1de-141">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="ef1de-142">Entwickler und Compileranbieter können Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider>-Implementierung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ef1de-142">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="ef1de-143">Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType>-Methode, um Sprachanbieter und Compilerkonfigurationseinstellungen auf einem Computer programmgesteuert aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="ef1de-143">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>

<span data-ttu-id="ef1de-144">Compilerelemente in der Anwendungs-oder Webkonfigurationsdatei können die Einstellungen in der Computer Konfigurationsdatei ergänzen oder überschreiben.</span><span class="sxs-lookup"><span data-stu-id="ef1de-144">Compiler elements in the application or Web configuration file can supplement or override the settings in the machine configuration file.</span></span> <span data-ttu-id="ef1de-145">Wenn mehr als eine Anbieter Implementierung für denselben Sprachnamen oder dieselbe Dateierweiterung konfiguriert ist, überschreibt die letzte übereinstimmende Konfiguration alle zuvor konfigurierten Anbieter für diesen Sprachnamen oder die Dateierweiterung.</span><span class="sxs-lookup"><span data-stu-id="ef1de-145">If more than one provider implementation is configured for the same language name or the same file extension, the last matching configuration overrides any previous configured providers for that language name or file extension.</span></span>

## <a name="configuration-file"></a><span data-ttu-id="ef1de-146">Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="ef1de-146">Configuration File</span></span>

<span data-ttu-id="ef1de-147">Dieses Element kann in der Computer Konfigurationsdatei und in der Anwendungs Konfigurationsdatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ef1de-147">This element can be used in the machine configuration file and the application configuration file.</span></span>

## <a name="example"></a><span data-ttu-id="ef1de-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ef1de-148">Example</span></span>

<span data-ttu-id="ef1de-149">Das folgende Beispiel veranschaulicht ein typisches compilerkonfigurationselement:</span><span class="sxs-lookup"><span data-stu-id="ef1de-149">The following example illustrates a typical compiler configuration element:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="ef1de-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef1de-150">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="ef1de-151">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="ef1de-151">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="ef1de-152">\<compilers>-Element</span><span class="sxs-lookup"><span data-stu-id="ef1de-152">\<compilers> Element</span></span>](compilers-element.md)
- [<span data-ttu-id="ef1de-153">Specifying Fully Qualified Type Names (Angeben vollqualifizierter Typnamen)</span><span class="sxs-lookup"><span data-stu-id="ef1de-153">Specifying Fully Qualified Type Names</span></span>](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="ef1de-154">[compiler-Element für compilers für compilation (ASP.NET-Einstellungsschema)](/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ef1de-154">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
