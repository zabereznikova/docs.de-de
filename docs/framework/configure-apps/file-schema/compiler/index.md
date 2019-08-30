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
ms.openlocfilehash: a651e4ca76fda9e65ea4a5848c19b1f0ebfe91b1
ms.sourcegitcommit: 1b020356e421a9314dd525539da12463d980ce7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2019
ms.locfileid: "70168930"
---
# <a name="compiler-and-language-provider-settings-schema"></a><span data-ttu-id="b4994-102">Schema für Compiler- und Sprachanbietereinstellungen</span><span class="sxs-lookup"><span data-stu-id="b4994-102">Compiler and Language Provider Settings Schema</span></span>
<span data-ttu-id="b4994-103">Die Compiler- und Sprachanbietereinstellungen geben Compilerkonfigurationselemente für verfügbare Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="b4994-103">Compiler and language provider settings specify compiler configuration elements for available language providers.</span></span> <span data-ttu-id="b4994-104">Jedes Compilerkonfigurationselement gibt den Typnamen des Codeanbieters, Compilerparameter, unterstützte Sprachnamen und unterstützte Dateierweiterungen an.</span><span class="sxs-lookup"><span data-stu-id="b4994-104">Each compiler configuration element specifies the code provider type name, compiler parameters, supported language names, and supported file extensions.</span></span>  
  
<span data-ttu-id="b4994-105">.NET Framework definiert die ursprünglichen Compilereinstellungen in der Computerkonfigurationsdatei (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="b4994-105">The .NET Framework defines the initial compiler settings in the machine configuration file (Machine.config).</span></span> <span data-ttu-id="b4994-106">Entwickler und Compileranbieter können Konfigurationseinstellungen für eine neue <xref:System.CodeDom.Compiler.CodeDomProvider>-Implementierung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b4994-106">Developers and compiler vendors can add configuration settings for a new <xref:System.CodeDom.Compiler.CodeDomProvider> implementation.</span></span> <span data-ttu-id="b4994-107">Verwenden Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType>-Methode, um Sprachanbieter und Compilerkonfigurationseinstellungen auf einem Computer programmgesteuert aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="b4994-107">Use the <xref:System.CodeDom.Compiler.CodeDomProvider.GetAllCompilerInfo%2A?displayProperty=nameWithType> method to programmatically enumerate language provider and compiler configuration settings on a computer.</span></span>  
  
[<span data-ttu-id="b4994-108"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="b4994-108">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="b4994-109">&nbsp;&nbsp;[ **\<System. CodeDom->** ](system-codedom-element.md)</span><span class="sxs-lookup"><span data-stu-id="b4994-109">&nbsp;&nbsp;[**\<system.codedom>**](system-codedom-element.md)</span></span>  
<span data-ttu-id="b4994-110">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Compiler >** ](compilers-element.md)</span><span class="sxs-lookup"><span data-stu-id="b4994-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<compilers>**](compilers-element.md)</span></span>  
<span data-ttu-id="b4994-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Compiler>** ](compiler-element.md)</span><span class="sxs-lookup"><span data-stu-id="b4994-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<compiler>**](compiler-element.md)</span></span>  
  
|<span data-ttu-id="b4994-112">Element</span><span class="sxs-lookup"><span data-stu-id="b4994-112">Element</span></span>|<span data-ttu-id="b4994-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b4994-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b4994-114">\<system.codedom></span><span class="sxs-lookup"><span data-stu-id="b4994-114">\<system.codedom></span></span>](system-codedom-element.md)|<span data-ttu-id="b4994-115">Gibt die Compilerkonfigurationseinstellungen für verfügbare Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="b4994-115">Specifies compiler configuration settings for available language providers.</span></span>|  
|[<span data-ttu-id="b4994-116">\<compilers></span><span class="sxs-lookup"><span data-stu-id="b4994-116">\<compilers></span></span>](compilers-element.md)|<span data-ttu-id="b4994-117">Der Container für Compilerkonfigurationselemente, dieser enthält 0 (null) oder mehr [\<compiler>](compiler-element.md)-Elemente.</span><span class="sxs-lookup"><span data-stu-id="b4994-117">Container for compiler configuration elements; contains zero or more [\<compiler>](compiler-element.md) elements.</span></span>|  
|[<span data-ttu-id="b4994-118">\<compiler></span><span class="sxs-lookup"><span data-stu-id="b4994-118">\<compiler></span></span>](compiler-element.md)|<span data-ttu-id="b4994-119">Gibt die Compilerkonfigurationsattribute für einen Sprachanbieter an.</span><span class="sxs-lookup"><span data-stu-id="b4994-119">Specifies the compiler configuration attributes for a language provider.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b4994-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4994-120">Example</span></span>  
 <span data-ttu-id="b4994-121">Das folgende Beispiel veranschaulicht ein typisches Compilerkonfigurationselement.</span><span class="sxs-lookup"><span data-stu-id="b4994-121">The following example illustrates a typical compiler configuration element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b4994-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4994-122">See also</span></span>

- <xref:System.CodeDom.Compiler.CompilerInfo>
- <xref:System.CodeDom.Compiler.CodeDomProvider>
- [<span data-ttu-id="b4994-123">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="b4994-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="b4994-124">\<compiler> Element</span><span class="sxs-lookup"><span data-stu-id="b4994-124">\<compiler> Element</span></span>](compiler-element.md)
