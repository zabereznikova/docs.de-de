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
ms.openlocfilehash: 9374fbaf7ceb61e5b72335417d32a08525477e0d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91149633"
---
# <a name="provideroption-element"></a><span data-ttu-id="9c8d8-102">\<providerOption>-Element</span><span class="sxs-lookup"><span data-stu-id="9c8d8-102">\<providerOption> Element</span></span>

<span data-ttu-id="9c8d8-103">Gibt die compilerversions-Attribute für einen Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="9c8d8-103">Specifies the compiler version attributes for a language provider.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<compiler>**](compiler-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<providerOption>**

## <a name="syntax"></a><span data-ttu-id="9c8d8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c8d8-104">Syntax</span></span>  
  
```xml  
<providerOption  
  name="option-name"  
  value="option-value"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9c8d8-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9c8d8-105">Attributes and Elements</span></span>  

 <span data-ttu-id="9c8d8-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9c8d8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9c8d8-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="9c8d8-107">Attributes</span></span>  
  
|<span data-ttu-id="9c8d8-108">attribute</span><span class="sxs-lookup"><span data-stu-id="9c8d8-108">Attribute</span></span>|<span data-ttu-id="9c8d8-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c8d8-109">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="9c8d8-110">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="9c8d8-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="9c8d8-111">Gibt den Namen der Option an. Beispiel: "Compilerversion".</span><span class="sxs-lookup"><span data-stu-id="9c8d8-111">Specifies the name of the option; for example, "CompilerVersion".</span></span>|  
|`value`|<span data-ttu-id="9c8d8-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="9c8d8-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="9c8d8-113">Gibt den Wert für die Option an. Beispiel: "v 3.5".</span><span class="sxs-lookup"><span data-stu-id="9c8d8-113">Specifies the value for the option; for example, "v3.5".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9c8d8-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9c8d8-114">Child Elements</span></span>  

 <span data-ttu-id="9c8d8-115">Keine</span><span class="sxs-lookup"><span data-stu-id="9c8d8-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9c8d8-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9c8d8-116">Parent Elements</span></span>  
  
|<span data-ttu-id="9c8d8-117">Element</span><span class="sxs-lookup"><span data-stu-id="9c8d8-117">Element</span></span>|<span data-ttu-id="9c8d8-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9c8d8-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9c8d8-119">\<configuration>-Element</span><span class="sxs-lookup"><span data-stu-id="9c8d8-119">\<configuration> Element</span></span>](../configuration-element.md)|<span data-ttu-id="9c8d8-120">Das Stammelement in jeder Konfigurationsdatei, die von der Common Language Runtime und den .NET Framework-Anwendungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9c8d8-120">The root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
|[<span data-ttu-id="9c8d8-121">\<system.codedom>-Element</span><span class="sxs-lookup"><span data-stu-id="9c8d8-121">\<system.codedom> Element</span></span>](system-codedom-element.md)|<span data-ttu-id="9c8d8-122">Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="9c8d8-122">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="9c8d8-123">\<compilers>-Element</span><span class="sxs-lookup"><span data-stu-id="9c8d8-123">\<compilers> Element</span></span>](compilers-element.md)|<span data-ttu-id="9c8d8-124">Container für Compilerkonfigurationselemente; enthält 0 (null) oder mehr- `<compiler>` Elemente.</span><span class="sxs-lookup"><span data-stu-id="9c8d8-124">Container for compiler configuration elements; contains zero or more `<compiler>` elements.</span></span>|  
|[<span data-ttu-id="9c8d8-125">\<compiler>-Element</span><span class="sxs-lookup"><span data-stu-id="9c8d8-125">\<compiler> Element</span></span>](compiler-element.md)|<span data-ttu-id="9c8d8-126">Gibt die Compilerkonfigurationsattribute für einen Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="9c8d8-126">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c8d8-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9c8d8-127">Remarks</span></span>  

 <span data-ttu-id="9c8d8-128">In der .NET Framework Version 3,5 können Code Document Object Model (CodeDom)-Code Anbieter anbieterspezifische Optionen mithilfe des-Elements unterstützen `<providerOption>` .</span><span class="sxs-lookup"><span data-stu-id="9c8d8-128">In the .NET Framework version 3.5, Code Document Object Model (CodeDOM) code providers can support provider-specific options by using the `<providerOption>` element.</span></span>  
  
 <span data-ttu-id="9c8d8-129">Der .NET Framework 3,5 umfasst aktualisierte .NET Framework 2,0-Assemblys und stellt neue Version 3,5-Assemblys bereit, die neue Typen enthalten.</span><span class="sxs-lookup"><span data-stu-id="9c8d8-129">The .NET Framework 3.5 includes updated .NET Framework 2.0 assemblies and provides new version 3.5 assemblies that contain new types.</span></span> <span data-ttu-id="9c8d8-130">Die Microsoft c#-und Visual Basic-Code Anbieter sind in .NET Framework 2,0-Assemblys enthalten, wurden jedoch aktualisiert, um Compiler der Version 3,5 zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="9c8d8-130">The Microsoft C# and Visual Basic code providers are contained in .NET Framework 2.0 assemblies but have been updated to support version 3.5 compilers.</span></span> <span data-ttu-id="9c8d8-131">Standardmäßig generieren die aktualisierten Code Anbieter Code für Compiler der Version 2,0.</span><span class="sxs-lookup"><span data-stu-id="9c8d8-131">By default, the updated code providers generate code for version 2.0 compilers.</span></span> <span data-ttu-id="9c8d8-132">Sie können das- `<providerOption>` Element verwenden, um die Ziel-Compilerversion in 3,5 zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9c8d8-132">You can use the `<providerOption>` element to change the target compiler version to 3.5.</span></span> <span data-ttu-id="9c8d8-133">Geben Sie hierzu "Compilerversion" für das `name` -Attribut und "v 3.5" für das- `value` Attribut an.</span><span class="sxs-lookup"><span data-stu-id="9c8d8-133">To do this, specify "CompilerVersion" for the `name` attribute and "v3.5" for the `value` attribute.</span></span> <span data-ttu-id="9c8d8-134">Sie müssen der Versionsnummer einen Kleinbuchstaben "v" voranstellen.</span><span class="sxs-lookup"><span data-stu-id="9c8d8-134">You must precede the version number with a lower-case "v".</span></span>  
  
 <span data-ttu-id="9c8d8-135">Sie können die Versions Spezifikation Global machen, indem Sie das- `<providerOption>` Element der Datei .NET Framework 2,0 Machine.config oder Root Web.config hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9c8d8-135">You can make the version specification global by adding the `<providerOption>` element to the .NET Framework 2.0 Machine.config or root Web.config file.</span></span> <span data-ttu-id="9c8d8-136">Wenn Sie die Standard-Compilerversion in der Machine.config-Datei auf 3,5 aktualisieren, können Sie Sie auf Anwendungs Basis wieder in 2,0 ändern, indem Sie das- `<providerOption>` Element in der Anwendungs Konfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="9c8d8-136">If you update the default compiler version to 3.5 in the Machine.config file, you can change it back to 2.0 on a per-application basis by using the `<providerOption>` element in the application configuration file.</span></span>  
  
 <span data-ttu-id="9c8d8-137">CodeDOM-Code Anbieter Implementierer können benutzerdefinierte Optionen verarbeiten, indem Sie einen Konstruktor bereitstellen, `providerOptions` der einen Parameter vom Typ annimmt <xref:System.Collections.Generic.IDictionary%602> .</span><span class="sxs-lookup"><span data-stu-id="9c8d8-137">CodeDOM code provider implementers can process custom options by providing a constructor that takes a `providerOptions` parameter of type <xref:System.Collections.Generic.IDictionary%602>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c8d8-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9c8d8-138">Example</span></span>  

 <span data-ttu-id="9c8d8-139">Im folgenden Beispiel wird veranschaulicht, wie angegeben wird, dass Version 3,5 des c#-Code Anbieters verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9c8d8-139">The following example demonstrates how to specify that version 3.5 of the C# code provider should be used.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9c8d8-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c8d8-140">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="9c8d8-141">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="9c8d8-141">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="9c8d8-142">\<compilers>-Element</span><span class="sxs-lookup"><span data-stu-id="9c8d8-142">\<compilers> Element</span></span>](compilers-element.md)
- [<span data-ttu-id="9c8d8-143">Specifying Fully Qualified Type Names (Angeben vollqualifizierter Typnamen)</span><span class="sxs-lookup"><span data-stu-id="9c8d8-143">Specifying Fully Qualified Type Names</span></span>](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)
- <span data-ttu-id="9c8d8-144">[compiler-Element für compilers für compilation (ASP.NET-Einstellungsschema)](/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="9c8d8-144">[compiler Element for compilers for compilation (ASP.NET Settings Schema)](/previous-versions/dotnet/netframework-4.0/a15ebt6c(v=vs.100))</span></span>
