---
title: Schema für Compiler- und Sprachanbietereinstellungen
ms.date: 03/30/2017
helpviewer_keywords:
- configuration settings [.NET Framework], compilers
- compiler configuration elements, schema
- compiler configuration elements
- language providers
- compiler configuration settings, schema
- configuration schema [.NET Framework], compiler settings
- language providers, settings schema
- compiler configuration settings
ms.assetid: c020b139-8699-4f0d-9ac9-70d0c5b2a8c8
ms.openlocfilehash: 5b1f9684ad26d4a03769af287fc8b0c0c7c4cc1a
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088681"
---
# <a name="compiler-and-language-provider-settings-schema"></a><span data-ttu-id="dd188-102">Schema für Compiler- und Sprachanbietereinstellungen</span><span class="sxs-lookup"><span data-stu-id="dd188-102">Compiler and Language Provider Settings Schema</span></span>
<span data-ttu-id="dd188-103">Die Compiler- und Sprachanbietereinstellungen geben Compilerkonfigurationselemente für verfügbare Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="dd188-103">Compiler and language provider settings specify compiler configuration elements for available language providers.</span></span> <span data-ttu-id="dd188-104">Jedes Compilerkonfigurationselement gibt den Typnamen des Codeanbieters, Compilerparameter, unterstützte Sprachnamen und unterstützte Dateierweiterungen an.</span><span class="sxs-lookup"><span data-stu-id="dd188-104">Each compiler configuration element specifies the code provider type name, compiler parameters, supported language names, and supported file extensions.</span></span>  
  
<span data-ttu-id="dd188-105">.NET Framework definiert die ursprünglichen Compilereinstellungen in der Computerkonfigurationsdatei (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="dd188-105">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="dd188-106">Entwickler und Compileranbieter können Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider>-Implementierung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="dd188-106">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="dd188-107">Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType>-Methode, um Sprachanbieter und Compilerkonfigurationseinstellungen auf einem Computer programmgesteuert aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="dd188-107">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
<span data-ttu-id="dd188-108">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dd188-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dd188-109">&nbsp;&nbsp;[ **\<System. CodeDom->** ](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="dd188-109">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span></span>\
<span data-ttu-id="dd188-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Compiler**](compilers-element.md) ></span><span class="sxs-lookup"><span data-stu-id="dd188-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)</span></span>\
<span data-ttu-id="dd188-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<- [ **Compiler>** ](compiler-element.md)</span><span class="sxs-lookup"><span data-stu-id="dd188-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<compiler>**](compiler-element.md)</span></span>
  
|<span data-ttu-id="dd188-112">Element</span><span class="sxs-lookup"><span data-stu-id="dd188-112">Element</span></span>|<span data-ttu-id="dd188-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dd188-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd188-114">\<system.codedom></span><span class="sxs-lookup"><span data-stu-id="dd188-114">\<system.codedom></span></span>](system-codedom-element.md)|<span data-ttu-id="dd188-115">Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="dd188-115">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="dd188-116">\<compilers></span><span class="sxs-lookup"><span data-stu-id="dd188-116">\<compilers></span></span>](compilers-element.md)|<span data-ttu-id="dd188-117">Der Container für Compilerkonfigurationselemente, dieser enthält 0 (null) oder mehr [\<compiler>](compiler-element.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="dd188-117">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>|  
|[<span data-ttu-id="dd188-118">\<compiler></span><span class="sxs-lookup"><span data-stu-id="dd188-118">\<compiler></span></span>](compiler-element.md)|<span data-ttu-id="dd188-119">Gibt die Compilerkonfigurationsattribute für einen Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="dd188-119">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dd188-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dd188-120">Example</span></span>  
 <span data-ttu-id="dd188-121">Das folgende Beispiel veranschaulicht ein typisches Compilerkonfigurationselement.</span><span class="sxs-lookup"><span data-stu-id="dd188-121">The following example illustrates a typical compiler configuration element.</span></span>  
  
```xml  
<configuration>  
   <system.codedom>  
     <compilers>  
       <!-- zero or more compiler elements -->  
       <compiler  
          language="c#;cs;csharp"  
          extension=".cs"  
          type="Microsoft.CSharp.CSharpCodeProvider, System, Version=1.0.5000.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
          compilerOptions=""  
          warningLevel="1" />  
     </compilers>  
   </system.codedom>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dd188-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd188-122">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="dd188-123">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="dd188-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="dd188-124">\<compiler> Element</span><span class="sxs-lookup"><span data-stu-id="dd188-124">\<compiler> Element</span></span>](compiler-element.md)
