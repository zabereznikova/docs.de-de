---
title: '&lt;ProviderOption&gt; Element'
ms.date: 03/30/2017
f1_keywords:
- provideroption
helpviewer_keywords:
- <provideroption> element
- providerOptions
- provideroption element
ms.assetid: 014f2e0b-c0b5-4fc4-92d3-73f02978b2a1
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 75cc2003a88cc7be467b9062c37b6b5d9eb82f53
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43564547"
---
# <a name="ltprovideroptiongt-element"></a><span data-ttu-id="bc181-102">&lt;ProviderOption&gt; Element</span><span class="sxs-lookup"><span data-stu-id="bc181-102">&lt;providerOption&gt; Element</span></span>
<span data-ttu-id="bc181-103">Gibt die Compiler-Version-Attribute für einen Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="bc181-103">Specifies the compiler version attributes for a language provider.</span></span>  
  
 <span data-ttu-id="bc181-104">\<Configuration-Element ></span><span class="sxs-lookup"><span data-stu-id="bc181-104">\<configuration Element></span></span>  
<span data-ttu-id="bc181-105">\<System.CodeDom-Element ></span><span class="sxs-lookup"><span data-stu-id="bc181-105">\<system.codedom Element></span></span>  
<span data-ttu-id="bc181-106">\<Compilers-Element ></span><span class="sxs-lookup"><span data-stu-id="bc181-106">\<compilers Element></span></span>  
<span data-ttu-id="bc181-107">\<Compilerfehler >-Element</span><span class="sxs-lookup"><span data-stu-id="bc181-107">\<compiler> Element</span></span>  
<span data-ttu-id="bc181-108">\<"Provideroption" >-Element</span><span class="sxs-lookup"><span data-stu-id="bc181-108">\<providerOption> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc181-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="bc181-109">Syntax</span></span>  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bc181-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bc181-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bc181-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bc181-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bc181-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="bc181-112">Attributes</span></span>  
  
|<span data-ttu-id="bc181-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="bc181-113">Attribute</span></span>|<span data-ttu-id="bc181-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc181-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="bc181-115">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="bc181-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="bc181-116">Gibt den Namen der Option. Beispiel: "CompilerVersion".</span><span class="sxs-lookup"><span data-stu-id="bc181-116">Specifies the name of the option; for example, "CompilerVersion".</span></span>|  
|`value`|<span data-ttu-id="bc181-117">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="bc181-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="bc181-118">Gibt den Wert für die Option an. z. B. "v3. 5".</span><span class="sxs-lookup"><span data-stu-id="bc181-118">Specifies the value for the option; for example, "v3.5".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bc181-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bc181-119">Child Elements</span></span>  
 <span data-ttu-id="bc181-120">Keine</span><span class="sxs-lookup"><span data-stu-id="bc181-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bc181-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bc181-121">Parent Elements</span></span>  
  
|<span data-ttu-id="bc181-122">Element</span><span class="sxs-lookup"><span data-stu-id="bc181-122">Element</span></span>|<span data-ttu-id="bc181-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc181-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bc181-124">\<configuration> Element</span><span class="sxs-lookup"><span data-stu-id="bc181-124">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|<span data-ttu-id="bc181-125">Das Stammelement in jeder Konfigurationsdatei, die von der Common Language Runtime und den .NET Framework-Anwendungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bc181-125">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="bc181-126">\<System.CodeDom >-Element</span><span class="sxs-lookup"><span data-stu-id="bc181-126">\<system.codedom> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/system-codedom-element.md)|<span data-ttu-id="bc181-127">Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="bc181-127">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="bc181-128">\<Compiler > Element</span><span class="sxs-lookup"><span data-stu-id="bc181-128">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)|<span data-ttu-id="bc181-129">Container für compilerkonfigurationselemente; enthält 0 (null) oder mehr `<compiler>` Elemente.</span><span class="sxs-lookup"><span data-stu-id="bc181-129">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
|[<span data-ttu-id="bc181-130">\<compiler> Element</span><span class="sxs-lookup"><span data-stu-id="bc181-130">\<compiler> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compiler-element.md)|<span data-ttu-id="bc181-131">Gibt die Compilerkonfigurationsattribute für einen Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="bc181-131">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc181-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bc181-132">Remarks</span></span>  
 <span data-ttu-id="bc181-133">In .NET Framework, Version 3.5, können Code Document Object Model (CodeDOM)-Codeanbieter anbieterspezifische Optionen unterstützen, mithilfe der `<providerOption>` Element.</span><span class="sxs-lookup"><span data-stu-id="bc181-133">In the .NET Framework version 3.5, Code Document Object Model (CodeDOM) code providers can support provider-specific options by using the `<providerOption>` element.</span></span>  
  
 <span data-ttu-id="bc181-134">.NET Framework 3.5 enthält aktualisierte .NET Framework 2.0-Assemblys sowie neue Assemblys der Version 3.5, die neue Typen enthalten.</span><span class="sxs-lookup"><span data-stu-id="bc181-134">The .NET Framework 3.5 includes updated .NET Framework 2.0 assemblies and provides new version 3.5 assemblies that contain new types.</span></span> <span data-ttu-id="bc181-135">Die Microsoft C#- und Visual Basic-Code-Anbieter sind in .NET Framework 2.0-Assemblys enthalten, aber es wurden aktualisiert, um die Version 3.5-Compiler unterstützen.</span><span class="sxs-lookup"><span data-stu-id="bc181-135">The Microsoft C# and Visual Basic code providers are contained in .NET Framework 2.0 assemblies but have been updated to support version 3.5 compilers.</span></span> <span data-ttu-id="bc181-136">Standardmäßig generiert die aktualisierten Codeanbieter Code für Version 2.0-Compiler.</span><span class="sxs-lookup"><span data-stu-id="bc181-136">By default, the updated code providers generate code for version 2.0 compilers.</span></span> <span data-ttu-id="bc181-137">Sie können die `<providerOption>` Element in der Ziel-Compilerversion 3.5 ändern.</span><span class="sxs-lookup"><span data-stu-id="bc181-137">You can use the `<providerOption>` element to change the target compiler version to 3.5.</span></span> <span data-ttu-id="bc181-138">Zu diesem Zweck geben Sie "CompilerVersion" für die `name` -Attribut und "v3. 5" für die `value` Attribut.</span><span class="sxs-lookup"><span data-stu-id="bc181-138">To do this, specify "CompilerVersion" for the `name` attribute and "v3.5" for the `value` attribute.</span></span> <span data-ttu-id="bc181-139">Sie müssen die Versionsnummer mit einem Kleinbuchstaben "V" voranstellen.</span><span class="sxs-lookup"><span data-stu-id="bc181-139">You must precede the version number with a lower-case "v".</span></span>  
  
 <span data-ttu-id="bc181-140">Sie können die Spezifikation der Version von der globalen vornehmen, durch das Hinzufügen der `<providerOption>` Elements, das die .NET Framework 2.0 "Machine.config" oder die Stammdatei "Web.config".</span><span class="sxs-lookup"><span data-stu-id="bc181-140">You can make the version specification global by adding the `<providerOption>` element to the .NET Framework 2.0 Machine.config or root Web.config file.</span></span> <span data-ttu-id="bc181-141">Wenn Sie die Standard-Compiler-Version 3.5 in der Datei Machine.config aktualisieren, können Sie es wieder in 2.0 auf einer Basis pro Anwendung ändern, mit der `<providerOption>` Element in der Konfigurationsdatei der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="bc181-141">If you update the default compiler version to 3.5 in the Machine.config file, you can change it back to 2.0 on a per-application basis by using the `<providerOption>` element in the application configuration file.</span></span>  
  
 <span data-ttu-id="bc181-142">CodeDOM-Code implementieren, können benutzerdefinierte Optionen verarbeiten, indem Sie einen Konstruktor bereitstellen, akzeptiert eine `providerOptions` Parameter vom Typ <xref:System.Collections.Generic.IDictionary%602>.</span><span class="sxs-lookup"><span data-stu-id="bc181-142">CodeDOM code provider implementers can process custom options by providing a constructor that takes a `providerOptions` parameter of type <xref:System.Collections.Generic.IDictionary%602>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc181-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc181-143">Example</span></span>  
 <span data-ttu-id="bc181-144">Das folgende Beispiel veranschaulicht das angeben, dass die Version 3.5 des C#-Code-Anbieters verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="bc181-144">The following example demonstrates how to specify that version 3.5 of the C# code provider should be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bc181-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc181-145">See Also</span></span>  
 <xref:System.CodeDom.Compiler.CompilerInfo>  
 <xref:System.CodeDom.Compiler.CodeDomProvider>  
 [<span data-ttu-id="bc181-146">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="bc181-146">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="bc181-147">\<Compiler > Element</span><span class="sxs-lookup"><span data-stu-id="bc181-147">\<compilers> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/compiler/compilers-element.md)  
 [<span data-ttu-id="bc181-148">Specifying Fully Qualified Type Names (Angeben vollqualifizierter Typnamen)</span><span class="sxs-lookup"><span data-stu-id="bc181-148">Specifying Fully Qualified Type Names</span></span>](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)  
 [<span data-ttu-id="bc181-149">Compiler-Element für Compilers für Compilation ((ASP.NET Einstellungsschema)</span><span class="sxs-lookup"><span data-stu-id="bc181-149">compiler Element for compilers for compilation (ASP.NET Settings Schema)</span></span>](https://msdn.microsoft.com/library/f7d6b078-5d42-4134-b3f7-62e1aba1df1e)
