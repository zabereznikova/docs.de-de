---
title: <providerOption>-Element
ms.date: 03/30/2017
f1_keywords:
- provideroption
helpviewer_keywords:
- <provideroption> element
- providerOptions
- provideroption element
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
ms.openlocfilehash: c8ba5b9a0680f5e5102c13eb5bb0c1904a168c07
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155400"
---
# <a name="provideroption-element"></a><span data-ttu-id="90d0e-102">\<ProviderOption> Element</span><span class="sxs-lookup"><span data-stu-id="90d0e-102">\<providerOption> Element</span></span>
<span data-ttu-id="90d0e-103">Gibt die Compilerversionsattribute für einen Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="90d0e-103">Specifies the compiler version attributes for a language provider.</span></span>  

<span data-ttu-id="90d0e-104">[**\<Konfiguration>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="90d0e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="90d0e-105">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="90d0e-105">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span></span>\
<span data-ttu-id="90d0e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<Compiler>**](compilers-element.md)</span><span class="sxs-lookup"><span data-stu-id="90d0e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)</span></span>\
<span data-ttu-id="90d0e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<Compiler->**](compiler-element.md)</span><span class="sxs-lookup"><span data-stu-id="90d0e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<compiler>**](compiler-element.md)</span></span>\
<span data-ttu-id="90d0e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<providerOption>**</span><span class="sxs-lookup"><span data-stu-id="90d0e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<providerOption>**</span></span>

## <a name="syntax"></a><span data-ttu-id="90d0e-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="90d0e-109">Syntax</span></span>  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90d0e-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="90d0e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="90d0e-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="90d0e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90d0e-112">Attributes</span><span class="sxs-lookup"><span data-stu-id="90d0e-112">Attributes</span></span>  
  
|<span data-ttu-id="90d0e-113">attribute</span><span class="sxs-lookup"><span data-stu-id="90d0e-113">Attribute</span></span>|<span data-ttu-id="90d0e-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90d0e-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="90d0e-115">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="90d0e-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="90d0e-116">Gibt den Namen der Option an. z. B. "CompilerVersion".</span><span class="sxs-lookup"><span data-stu-id="90d0e-116">Specifies the name of the option; for example, "CompilerVersion".</span></span>|  
|`value`|<span data-ttu-id="90d0e-117">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="90d0e-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="90d0e-118">Gibt den Wert für die Option an. z. B. "v3.5".</span><span class="sxs-lookup"><span data-stu-id="90d0e-118">Specifies the value for the option; for example, "v3.5".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="90d0e-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="90d0e-119">Child Elements</span></span>  
 <span data-ttu-id="90d0e-120">Keine.</span><span class="sxs-lookup"><span data-stu-id="90d0e-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="90d0e-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="90d0e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="90d0e-122">Element</span><span class="sxs-lookup"><span data-stu-id="90d0e-122">Element</span></span>|<span data-ttu-id="90d0e-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90d0e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="90d0e-124">\<Konfiguration> Element</span><span class="sxs-lookup"><span data-stu-id="90d0e-124">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="90d0e-125">Das Stammelement in jeder Konfigurationsdatei, die von der Common Language Runtime und den .NET Framework-Anwendungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="90d0e-125">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="90d0e-126">\<system.codedom> Element</span><span class="sxs-lookup"><span data-stu-id="90d0e-126">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="90d0e-127">Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="90d0e-127">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="90d0e-128">\<Compiler> Element</span><span class="sxs-lookup"><span data-stu-id="90d0e-128">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="90d0e-129">Container für Compilerkonfigurationselemente; enthält null `<compiler>` oder mehr Elemente.</span><span class="sxs-lookup"><span data-stu-id="90d0e-129">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
|[<span data-ttu-id="90d0e-130">\<Compiler> Element</span><span class="sxs-lookup"><span data-stu-id="90d0e-130">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="90d0e-131">Gibt die Compilerkonfigurationsattribute für einen Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="90d0e-131">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90d0e-132">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="90d0e-132">Remarks</span></span>  
 <span data-ttu-id="90d0e-133">In .NET Framework Version 3.5 können CodeDOM-Codeanbieter (Code Document Object Model) `<providerOption>` anbieterspezifische Optionen mithilfe des Elements unterstützen.</span><span class="sxs-lookup"><span data-stu-id="90d0e-133">In the .NET Framework version 3.5, Code Document Object Model (CodeDOM) code providers can support provider-specific options by using the `<providerOption>` element.</span></span>  
  
 <span data-ttu-id="90d0e-134">.NET Framework 3.5 enthält aktualisierte .NET Framework 2.0-Assemblys und stellt neue Assemblys der Version 3.5 bereit, die neue Typen enthalten.</span><span class="sxs-lookup"><span data-stu-id="90d0e-134">The .NET Framework 3.5 includes updated .NET Framework 2.0 assemblies and provides new version 3.5 assemblies that contain new types.</span></span> <span data-ttu-id="90d0e-135">Die Microsoft-Codeanbieter für C- und Visual Basic sind in .NET Framework 2.0-Assemblys enthalten, wurden jedoch aktualisiert, um Compiler der Version 3.5 zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="90d0e-135">The Microsoft C# and Visual Basic code providers are contained in .NET Framework 2.0 assemblies but have been updated to support version 3.5 compilers.</span></span> <span data-ttu-id="90d0e-136">Standardmäßig generieren die aktualisierten Codeanbieter Code für Compiler der Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="90d0e-136">By default, the updated code providers generate code for version 2.0 compilers.</span></span> <span data-ttu-id="90d0e-137">Sie können `<providerOption>` das Element verwenden, um die Zielcompilerversion in 3.5 zu ändern.</span><span class="sxs-lookup"><span data-stu-id="90d0e-137">You can use the `<providerOption>` element to change the target compiler version to 3.5.</span></span> <span data-ttu-id="90d0e-138">Geben Sie dazu "CompilerVersion" `name` für das Attribut und "v3.5" für das `value` Attribut an.</span><span class="sxs-lookup"><span data-stu-id="90d0e-138">To do this, specify "CompilerVersion" for the `name` attribute and "v3.5" for the `value` attribute.</span></span> <span data-ttu-id="90d0e-139">Sie müssen der Versionsnummer mit einem "v" in Kleinbuchstaben vorangehen.</span><span class="sxs-lookup"><span data-stu-id="90d0e-139">You must precede the version number with a lower-case "v".</span></span>  
  
 <span data-ttu-id="90d0e-140">Sie können die Versionsspezifikation global `<providerOption>` machen, indem Sie das Element zur Datei .NET Framework 2.0 Machine.config oder root Web.config hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="90d0e-140">You can make the version specification global by adding the `<providerOption>` element to the .NET Framework 2.0 Machine.config or root Web.config file.</span></span> <span data-ttu-id="90d0e-141">Wenn Sie die Standardcompilerversion in der Datei Machine.config auf 3.5 aktualisieren, können Sie sie pro `<providerOption>` Anwendung auf 2.0 zurücksetzen, indem Sie das Element in der Anwendungskonfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="90d0e-141">If you update the default compiler version to 3.5 in the Machine.config file, you can change it back to 2.0 on a per-application basis by using the `<providerOption>` element in the application configuration file.</span></span>  
  
 <span data-ttu-id="90d0e-142">CodeDOM-Codeanbieterimplementierer können benutzerdefinierte Optionen verarbeiten, indem `providerOptions` sie <xref:System.Collections.Generic.IDictionary%602>einen Konstruktor bereitstellen, der einen Parameter vom Typ annimmt.</span><span class="sxs-lookup"><span data-stu-id="90d0e-142">CodeDOM code provider implementers can process custom options by providing a constructor that takes a `providerOptions` parameter of type <xref:System.Collections.Generic.IDictionary%602>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90d0e-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90d0e-143">Example</span></span>  
 <span data-ttu-id="90d0e-144">Im folgenden Beispiel wird veranschaulicht, wie Sie angeben, dass Version 3.5 des Codeanbieters verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="90d0e-144">The following example demonstrates how to specify that version 3.5 of the C# code provider should be used.</span></span>  
  
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
        warningLevel="1" >  
          <providerOption  
            name="CompilerVersion"  
            value="v3.5" />  
      </compiler>  
    </compilers>  
  </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="90d0e-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90d0e-145">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="90d0e-146">Schema der Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="90d0e-146">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="90d0e-147">\<Compiler> Element</span><span class="sxs-lookup"><span data-stu-id="90d0e-147">\<compilers> Element</span></span>](compilers-element.md)
- [<span data-ttu-id="90d0e-148">Angeben vollständig gekennzeichneter Typnamen</span><span class="sxs-lookup"><span data-stu-id="90d0e-148">Specifying Fully Qualified Type Names</span></span>](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="90d0e-149">[compiler-Element für compilers für compilation (ASP.NET-Einstellungsschema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="90d0e-149">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
